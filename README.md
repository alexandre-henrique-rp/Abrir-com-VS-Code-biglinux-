# Adicionando a Opção "Abrir com VS Code" no Menu de Contexto do Dolphin (BigLinux)

Este guia explica como adicionar a opção **"Abrir com VS Code"** ao menu de contexto do **Dolphin** no **BigLinux**.

---

## 📌 Passo 1: Criar o Arquivo do Serviço
Abra o terminal e crie o arquivo do atalho:
```bash
mkdir -p ~/.local/share/kservices5/ServiceMenus/
nano ~/.local/share/kservices5/ServiceMenus/code.desktop
```

Cole o seguinte conteúdo no arquivo:
```ini
[Desktop Entry]
Type=Service
ServiceTypes=KonqPopupMenu/Plugin
MimeType=inode/directory
Actions=openWithVSCode
X-KDE-Priority=TopLevel

[Desktop Action openWithVSCode]
Name=Abrir com VS Code
Exec=code "%U"
Icon=/usr/share/code/resources/app/out/media/code-icon.svg
```
Salve o arquivo pressionando `Ctrl + X`, depois `S` e `Enter`.

---

## 📌 Passo 2: Atualizar o KDE para Reconhecer o Serviço
Execute o seguinte comando para atualizar o cache do KDE:
```bash
kbuildsycoca5
```

---

## 📌 Passo 3: Testar o Novo Atalho
Agora, clique com o **botão direito** dentro de uma pasta no Dolphin. Você verá a opção **"Abrir com VS Code"** com o ícone do VS Code. 🎨

Se a opção não aparecer imediatamente, reinicie o Dolphin:
```bash
killall dolphin && dolphin &
```

---

## 🎨 Personalizando o Ícone
Caso queira usar um ícone diferente, basta substituir a linha `Icon=/usr/share/code/resources/app/out/media/code-icon.svg` por um caminho válido para outro ícone. Para listar ícones disponíveis, use:
```bash
ls /usr/share/icons/hicolor/scalable/apps/
```

Se tiver um ícone personalizado, especifique o caminho completo, como:
```ini
Icon=/caminho/para/seu/icone.png
```

---

Agora, toda vez que quiser abrir uma pasta no VS Code, basta clicar com o **botão direito**! 🚀🔥

