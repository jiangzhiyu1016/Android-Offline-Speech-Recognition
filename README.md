# Android-Offline-Speech-Recognition
Provide accurate offline voice-to-text services for VR,AR and Android platforms, such as oculus quest1/2/pro or pico3/4


详细介绍:
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

## New Project
1.If you are a blueprint plug-in, you need to create a C++ class
![image](https://user-images.githubusercontent.com/56686900/211325300-1baeb505-ce22-4a2c-8eba-6f0c642701bf.png)
![image](https://user-images.githubusercontent.com/56686900/211325399-4aa0fd58-1e7c-48b3-ac37-f5acb1d41e26.png)
If it is UE5.0 or below, create a new C++ class in the file TAB



2.Visual studio opens after you create a new C++ class
You can select debug directly, if there is a problem you can right-click the project and select rebuild solution
![image](https://user-images.githubusercontent.com/56686900/211325917-dc74b38f-3896-4df7-bf08-bfed6a07c7c5.png)

## How To call our plugin
1.Make sure that Jvoice Plugin is enabled in your plugin
2.For example
![image](https://user-images.githubusercontent.com/56686900/211327521-9ebb311b-09f7-4f18-8704-d55e2379febf.png)

## function declaration
1.Jvoice_Execute(float Param,FString info);
* Param: Alternate parameter, can be random floating point number
* info = "1": Initialization model 
* info = "2": Enable or disable voice input
* info = "3": The interface is reserved. You are advised to use info=6
* info = "4": The interface is reserved. You are advised to use info=6
* info = "5": Reset the text of the model. After the call, the model returns the text to zero
* info = "6": Read speech and convert text in a thread in real time,Calling it again terminates the thread

2.getJvoicePointer()
getJvoicePointer() gets an object that can bind real-time speech-to-text results to events

备注:
本项目的kotlin部分来自开源项目https://github.com/k2-fsa/sherpa-ncnn
