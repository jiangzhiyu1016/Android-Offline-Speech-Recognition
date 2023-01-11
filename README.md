# Android-Offline-Speech-Recognition
Provide accurate offline voice-to-text services for VR,AR and Android platforms, such as oculus quest1/2/pro or pico3/4


## Introduction
1.支持两种语音离线识别(英语和汉语) 
1. Support two kinds of offline speech recognition (English and Chinese)
2.简单,强大,创作者可以用几个蓝图函数轻松调用它
2. Simple and powerful, creators can easily call it with several blueprint functions
3.不依赖任何其他服务,调用插件,打包android arm64就可以运行
3. Do not rely on any other services, call plug-in, package android arm64 can run
4.为VR耳机开发,所以它超适合 oculus quest1/2/pro or pico3/4 
我会提供一个VR一体机例子
4. Developed for VR headsets, so it's super suitable for oculus quest1/2/pro or pico3/4
I'll give you an example of a VR all-in-one

How To Use:

## Project Settings--Android
* Build--Only Choose Support arm64 [aka arm64-v8a]
* Advanced APK Packaging--Add permissions to support Voice chat (RECORD_AUDIO)


## How To call our plugin
1.Make sure that Jvoice Plugin is enabled in your plugin
2.For example
![image](https://user-images.githubusercontent.com/56686900/211327521-9ebb311b-09f7-4f18-8704-d55e2379febf.png)

## function declaration
### 1.Jvoice_Execute(float Param,FString info);
* Param: Alternate parameter, can be random floating point number
* info = "1": Initialization model(Don't repeat calls)
* info = "2": Initialization audio(Don't repeat calls)
* info = "3": The interface is reserved. You are advised to use info=6
* info = "4": The interface is reserved. You are advised to use info=6
* info = "5": Reset the text of the model. After the call, the model returns the text to zero
* info = "6": Read speech and convert text in a thread in real time,Calling it again terminates the thread

### 2.getJvoicePointer()
* getJvoicePointer() gets an object that can bind real-time speech-to-text results to events

## Call routine diagram summary

![image](https://user-images.githubusercontent.com/56686900/211331329-d5455b96-0538-41d8-a3d9-b60348351e63.png)

1.Complete process, start real-time voice to text
![image](https://user-images.githubusercontent.com/56686900/211331569-46e2a2d1-9f41-41d4-acf7-33442d1b3c96.png)
2. the model returns the text to zero
![image](https://user-images.githubusercontent.com/56686900/211331789-7bd7c4f0-1796-4b1a-ba30-90a4365b6e5a.png)
3.Stop converting speech to text/Start converting speech to text

![image](https://user-images.githubusercontent.com/56686900/211445655-dcb8da3a-bb2a-4e9d-b4ea-abb6cac723fb.png)

## Common errors
### Jvoice plug-in cannot be found if packaged on Android phone
1.If you are a blueprint plug-in, you need to create a C++ class
![image](https://user-images.githubusercontent.com/56686900/211325300-1baeb505-ce22-4a2c-8eba-6f0c642701bf.png)

If it is UE5.0 or below, create a new C++ class in the file TAB

![image](https://user-images.githubusercontent.com/56686900/211325399-4aa0fd58-1e7c-48b3-ac37-f5acb1d41e26.png)


2.Visual studio opens after you create a new C++ class
You can select debug directly, if there is a problem you can right-click the project and select rebuild solution
![image](https://user-images.githubusercontent.com/56686900/211325917-dc74b38f-3896-4df7-bf08-bfed6a07c7c5.png)

备注:
本项目的kotlin部分来自开源项目https://github.com/k2-fsa/sherpa-ncnn
