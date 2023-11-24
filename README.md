# NotifyDCSPMAttackPathByJapanese
Defender CSPM の攻撃パスを Azure OpenAI を用いて日本語で通知するテンプレートです。

# 通知イメージ
- O365 コネクタを用いてメール送信します。
- テンプレートは [Global で提供されたテンプレート](https://github.com/Azure/Microsoft-Defender-for-Cloud/tree/main/Workflow%20automation/Notify-NewAttackPath)を Azure Open AI を用いるロジックにカスタマイズしています。
<img width="313" alt="image" src="https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/651b0432-ed14-47ae-b6dd-99ce041c10c5">

# デプロイ方法

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhisashin0728%2FNotifyDCSPMAttackPathByJapanese%2Fmain%2Ftemplate.json)
