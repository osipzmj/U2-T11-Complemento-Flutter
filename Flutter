# Flutter aplicaciones

## YesOrNo
### Código

- main.dart
```
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:yes_no_app/presentation/screens/chat/chat_screen.dart';

import 'config/theme/app_theme.dart';
import 'presentation/providers/chat_provider.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MultiProvider(
      providers: [ChangeNotifierProvider(create: (_) => ChatProvider())],
      child: MaterialApp(
          title: 'Yes No App',
          debugShowCheckedModeBanner: false,
          theme: AppTheme(selectedColor: 1).theme(),
          home: const ChatScreem()),
    );
  }
}

```
- chat-screen.dart
```
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:yes_no_app/domain/entitites/message.dart';
import 'package:yes_no_app/presentation/providers/chat_provider.dart';
import 'package:yes_no_app/presentation/widgets/chat/her_message_bubble.dart';
import 'package:yes_no_app/presentation/widgets/shared/message_filed_box.dart';

import '../../widgets/chat/my_message_bubble.dart';

class ChatScreem extends StatelessWidget {
  const ChatScreem({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
          leading: const Padding(
            padding: EdgeInsets.all(4.0),
            child: CircleAvatar(
              backgroundImage: NetworkImage(
                  'https://www.google.com/url?sa=i&url=https%3A%2F%2Fes.linkedin.com%2Fpulse%2Fqu%25C3%25A9-es-el-skibidi-toilet-y-por-la-sensaci%25C3%25B3n-en-internet-adrian-lara&psig=AOvVaw0Z1ipoKk2HhjUZrQAgdHen&ust=1720222700468000&source=images&cd=vfe&opi=89978449&ved=0CA8QjRxqFwoTCIjt3IrHjocDFQAAAAAdAAAAABAE'),
            ),
          ),
          title: const Text('Usuario'),
          centerTitle: false),
      body: _ChatView(),
    );
  }
}

class _ChatView extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final chatProvider = context.watch<ChatProvider>();

    return SafeArea(
      child: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 10),
        child: Column(children: [
          Expanded(
              child: ListView.builder(
                  controller: chatProvider.chatScrollController,
                  itemCount: chatProvider.messagesList.length,
                  itemBuilder: (contex, index) {
                    final message = chatProvider.messagesList[index];
                    return (message.fromWho == FromWho.hers)
                        ? HerMessageBubble(message: message)
                        : MyMessageBubble(message: message);
                  })),

          ///Caja de texto

          MessageFieldBox(
            onValue: chatProvider.sendMessage,
          ),
        ]),
      ),
    );
  }
}

```
- chat_provider.dart
```
import 'package:flutter/material.dart';

import '../../domain/entitites/message.dart';
import '../../helpers/get_yes_no_answer.dart';

class ChatProvider extends ChangeNotifier {
  final chatScrollController = ScrollController();
  final getYesNoAnswer = GetYesNoAnswer();

  List<Message> messagesList = [
    Message(text: 'Hola Mundo', fromWho: FromWho.me),
    Message(text: 'Lorem', fromWho: FromWho.me)
  ];

  Future<void> sendMessage(String text) async {
    if (text.isEmpty) return;
    final newMessage = Message(text: text, fromWho: FromWho.me);
    messagesList.add(newMessage);
    if (text.endsWith('?')) {
      herReply();
    }

    notifyListeners();
    await moveScrollToBottom();
  }

  Future<void> herReply() async {
    final herMessage = await getYesNoAnswer.getAnswer();
    messagesList.add(herMessage);
    notifyListeners();
    await moveScrollToBottom();
  }

  Future<void> moveScrollToBottom() async {
    await Future.delayed(const Duration(milliseconds: 100));

    chatScrollController.animateTo(
        chatScrollController.position.maxScrollExtent,
        duration: const Duration(milliseconds: 300),
        curve: Curves.easeOut);
  }
}

```

- yes_no_models.dart
```
import 'dart:convert';

import 'package:yes_no_app/domain/entitites/message.dart';

class YesNoModel {
    final String answer;
    final bool forced;
    final String image;

    YesNoModel({
        required this.answer,
        required this.forced,
        required this.image,
    });

    factory YesNoModel.fromJsonMap(Map<String, dynamic> json) => YesNoModel(
        answer: json["answer"],
        forced: json["forced"],
        image: json["image"],
    );

    Map<String, dynamic> toJson() => {
        "answer": answer,
        "forced": forced,
        "image": image,
    };

    Message toMeddageEntity()=>Message(
      text: answer == 'yes' ? 'si':'no', 
      fromWho: FromWho.hers,
      imageUrl: image
      );
}


```

- message.dart
```
enum FromWho { me, hers }

class Message {
  final String text;
  final String? imageUrl;
  final FromWho fromWho;

  Message({required this.text, this.imageUrl, required this.fromWho});
}

```

- her_message_bubble.dart
```
import 'dart:ui';

import 'package:flutter/material.dart';

import '../../../domain/entitites/message.dart';

class HerMessageBubble extends StatelessWidget {
  const HerMessageBubble({super.key, required this.message});

  final Message message;

  @override
  Widget build(BuildContext context) {
    final colors = Theme.of(context).colorScheme;

    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Container(
            decoration: BoxDecoration(
              color: colors.secondary,
              borderRadius: BorderRadius.circular(20),
            ),
            child: Padding(
              padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 10),
              child: Text(message.text, style: TextStyle(color: Colors.white)),
            )),
        const SizedBox(
          height: 10,
        ),
        _ImageBubble(imageUrl: message.imageUrl!),
        const SizedBox(
          height: 10,
        ),
      ],
    );
  }
}

class _ImageBubble extends StatelessWidget {
  const _ImageBubble({required this.imageUrl});

  final String imageUrl;

  @override
  Widget build(BuildContext context) {
    final size = MediaQuery.of(context).size;

    return ClipRRect(
        borderRadius: BorderRadius.circular(20),
        child: Image.network(
          imageUrl,
          width: size.width * 0.7,
          height: 150,
          fit: BoxFit.cover,
          loadingBuilder: (contex, child, loadingProgress) {
            if (loadingProgress == null) return child;

            return Container(
                width: size.width * 0.7,
                height: 150,
                padding:
                    const EdgeInsets.symmetric(horizontal: 10, vertical: 5),
                child: const Text('esta enviando una imagen'));
          },
        ));
  }
}

```

- my_message_bubble.dart
```
import 'package:flutter/material.dart';

import '../../../domain/entitites/message.dart';

class MyMessageBubble extends StatelessWidget {
  
  final Message message;
  
  const MyMessageBubble
({super.key,
  required this.message
});

  @override
  Widget build(BuildContext context) {

final colors = Theme.of(context).colorScheme;

    return   Column(
      crossAxisAlignment: CrossAxisAlignment.end,
      children:  [
        Container(
          decoration: BoxDecoration(
            color: colors.primary,
            borderRadius: BorderRadius.circular(20),
            ),
          child:  Padding(
            padding:  const EdgeInsets.symmetric(horizontal: 20, vertical: 10),
            child: Text(message.text,style:const TextStyle(color:Colors.white)),
          )
          ),
        const SizedBox(height: 10,)
      ],
     
    );
  }
}

```

### Imágenes
