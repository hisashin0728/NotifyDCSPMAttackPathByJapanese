# NotifyDCSPMAttackPathByJapanese
Defender CSPM の攻撃パスを Azure OpenAI を用いて日本語で通知するテンプレートです。

# 1. 通知イメージ
- O365 コネクタを用いてメール送信します。
- テンプレートは [Global で提供されたテンプレート](https://github.com/Azure/Microsoft-Defender-for-Cloud/tree/main/Workflow%20automation/Notify-NewAttackPath)を Azure Open AI を用いるロジックにカスタマイズしています。

![image](https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/6388a7e8-655e-4701-9607-8468058a5461)

# 2. 事前準備
Defender CSPM で検知される攻撃パスを補完するための専用 Azure Storage、およびテーブル名 ``AttachPaths`` を作成して下さい。
ドメイン名が必要になるので、保存しておいてください。
![image](https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/c9c70a1d-948d-4f7b-be87-0ec333ce984c)
ロジックアプリのコネクタから接続するため、認証キーを保存しておいてください。
<img width="788" alt="image" src="https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/88abb71c-d39f-4b82-a736-a93dfd79058f">

# 3. デプロイ方法

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhisashin0728%2FNotifyDCSPMAttackPathByJapanese%2Fmain%2Ftemplate.json)

- Deploy 時に必要なパラメータを設定してください。
![image](https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/0169e796-c991-4b00-a7ad-ed95e5c59147)

# 4. デプロイ後の設定
## 4.1 コネクタ認証
- O365 コネクタ ``Office365-attackPathNotification`` より、送信元メールアドレスの認証を行い、保存してください。
<img width="1119" alt="image" src="https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/de65c36f-9a2a-4c0e-9599-7964434ec082">

- Azure Storage コネクタ ``Azuretables-attackPathNotification`` より、ストレージアカウントのドメイン名と認証キーを設定して保存してください。
<img width="1116" alt="image" src="https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/eaab5a43-5da7-4e4e-ae99-e7010b7e53bc">

## 4.2 マネージドIDの認証
- ロジックアプリのマネージドID認証として、該当サブスクリプションの「閲覧者」権限と「Azure OpenAI User」の権限を付与して下さい。
<img width="948" alt="image" src="https://github.com/hisashin0728/NotifyDCSPMAttackPathByJapanese/assets/55295601/49008205-6036-4da5-929b-e9562c1aecf3">
