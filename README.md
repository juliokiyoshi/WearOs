# WearOs
 This file is a summary of all the research I found about Wear:

## Configuraçes Iniciais:

### Como debugar o projeto no relógio:
1. Primeiro é necessário habilitar o modo de desenvolvedor no relógio:https://developer.android.com/training/wearables/apps/debugging?hl=pt-br
2. Depois de habilitar o modo desenvolvedor ative a ```depuração ADB```  e depuração via Bluetooth.
3. No aplicativo do celular (WearOs), click em configurações avançadas e ative depuração via Bluetooth
4. Agora no seu computador abra o terminal e digite os seguintes comandos:
```
sudo adb forward tcp:6666 localabstract:/adb-hub
adb connect localhost:6666
```
Para verificar se funcionou digite o seguinte comando:
```
adb devices
```
Resultado será algo parecido com isto:
![image](https://user-images.githubusercontent.com/38574345/140073077-b5ec7ff7-3f76-4a08-bfc3-dca88ccfb5fc.png)

5.Agora o seu relógio irá aparece no Android Studio para testar o seu APP, como mostra a imagem abaixo:

![image](https://user-images.githubusercontent.com/38574345/140073513-c6b7ec6f-640c-4591-9e54-eb685135de59.png)

Referência: https://www.ranorex.com/help/latest/web-mobile-testing/advanced-mobile-testing/testing-android-wear-apps/

## Criando uma aplicação para o relógio:

* Referência para criar um projeto WearOs App: https://developer.android.com/training/wearables/get-started/creating

OBS: Para desenvolver uma aplicação para o relógio é necessário instanciar um projeto no Android Studio com sdk minima de ```minSdk 25```

* A estrutura de Pastas para um Projeto que tenha um App de mobile e um App de Celular:

![image](https://user-images.githubusercontent.com/38574345/140073844-98bed839-edfc-45c1-9218-aa9f433bcd11.png)


## Tutoriais básicos para inicar o desenvolvimento de aplicações Wear:
*  Wear Tiles:https://developer.android.com/codelabs/wear-tiles#0
*  Watch Face: https://developer.android.com/codelabs/complications?hl=en&continue=https%3A%2F%2Fcodelabs.developers.google.com%2F#0
*  Compose for Wear OS Codelab (Esse Code Lab é necessário ter um sdk minima 30 para usar o Jetpack Compose) https://developer.android.com/codelabs/compose-for-wear-os?hl=en&continue=https%3A%2F%2Fcodelabs.developers.google.com%2F#0
* Ongoing Activity API: https://developer.android.com/codelabs/ongoing-activity?hl=en&continue=https%3A%2F%2Fcodelabs.developers.google.com%2F#0

## Informações Basicas:

### Construção de telas para o Wear:
Referência:https://developer.android.com/training/wearables/overlays/layouts

### Overlays:
Referência:https://developer.android.com/training/wearables/overlays

### Navegação entre overlays:
Recomendação do próprio Desenvolvedor(utilizar navegações entre Activities):
```
We strongly recommend you use this approach. It simplifies your code and an activity automatically supports swipe-to-dismiss. This also makes implementing ambient mode simpler.
```
Pode ser feito da seguinte maneira, utilizando uma Intent para fazer a mudança de overlay:
```
   binding.btnStart.setOnClickListener {
            val switchActivityIntent = Intent(this, Activity_secundary::class.java)
            startActivity(switchActivityIntent)
        }
```
Referência:https://developer.android.com/training/wearables/overlays/navigation

### Troca de dados entre App mobile e App Wear:
* Enviar e receber mensagens no Wear:
https://developer.android.com/training/wearables/data-layer/messages

* Gerenciar eventos de Data Layer no Wear:

https://developer.android.com/training/wearables/data-layer/events#Listen





