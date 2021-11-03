# WearOs

## This file is a summary of all the research I found about Wear:

## Configuraçes Iniciais:

### Como debugar o projeto no relógio:
1. Primeiro é necessário habilitar o modo de desenvolvedor no relógio:https://developer.android.com/training/wearables/apps/debugging?hl=pt-br
2. Depois de habilitar o modo desenvolvedor ative a ```depuração ADB```  e depuração via Bluetooth.
3. No aplicativo do celular (WearOs), click em configurações avançadas e ative depuração via Bluetooth
4. Agora no seu computador abra o terminale digite os seguintes comandos:
```
sudo adb forward tcp:6666 localabstract:/adb-hub
adb connect localhost:6666

//Para verificar se funcionou

adb devices
```
Resultado seria algo parecido com isto:
![image](https://user-images.githubusercontent.com/38574345/140073077-b5ec7ff7-3f76-4a08-bfc3-dca88ccfb5fc.png)

5. Agora o seu relógio irá aparecer no android studio agora bastar rodar o projeto Wear para testar nele.

![image](https://user-images.githubusercontent.com/38574345/140073513-c6b7ec6f-640c-4591-9e54-eb685135de59.png)

Referência: https://www.ranorex.com/help/latest/web-mobile-testing/advanced-mobile-testing/testing-android-wear-apps/

### Configuraçes do projeto para o relógio:

Para desenvolver uma aplicação para o relógio é necessário instanciar um projeto no Android Studio com sdk minima de ```minSdk 25```

A estrutura de Pastas do Projeto é dado por:

![image](https://user-images.githubusercontent.com/38574345/140073844-98bed839-edfc-45c1-9218-aa9f433bcd11.png)

### Construção de telas para o Wear:
Referencia:https://developer.android.com/training/wearables/overlays/layouts

### Overlays:
Referencia:https://developer.android.com/training/wearables/overlays

### Navegação entre overlays:
Recomendação do próprio Desenvolvedor(utilizar navegaçes entre Activities):
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

Referencia:https://developer.android.com/training/wearables/overlays/navigation







