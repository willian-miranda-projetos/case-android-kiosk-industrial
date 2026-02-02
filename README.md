# Projeto Totem SCP – Kiosk Android (Estaleiro Mauá)

## 📌 Contexto

Este projeto documenta a implementação de um **ambiente Android controlado (kiosk)** para uso operacional no **Estaleiro Mauá**.

O objetivo foi disponibilizar o sistema **SCP**  
🔗 https://scp.estaleiromaua.ind.br  

em dispositivos móveis **Lenovo**, permitindo que **coordenadores de equipes** auxiliem clientes no processo de:
- criação de pedidos
- validação de informações
- assinatura diretamente no sistema

Tudo isso **sem permitir acesso ao Android**, configurações do dispositivo ou outros aplicativos.

---

## 🎯 Objetivo do Projeto

- Restringir o uso do Android apenas ao sistema SCP
- Garantir inicialização automática do sistema ao ligar o dispositivo
- Impedir acesso a configurações, barra de status e outros apps
- Não utilizar soluções pagas ou MDMs corporativos
- Utilizar apenas soluções gratuitas disponíveis na Play Store

---

## ⚙️ Desafios Encontrados

- Android com limitações para modo kiosk sem Device Owner
- Falhas em soluções MDM devido a bloqueios do fabricante
- Limitações de versões gratuitas de apps kiosk
- Necessidade de estabilidade em ambiente industrial
- Proibição de custos adicionais com licenças

---

## 🧠 Solução Final Adotada

Após testes com diversas abordagens (WebView, Custom Tabs, MDM, Android Enterprise), foi definida uma solução **híbrida e funcional**, utilizando **dois aplicativos gratuitos que se complementam**.

### 🔹 Aplicativos Utilizados

#### 1️⃣ Fully Kiosk Browser & App Lockdown
**Função:**
- Abrir o sistema SCP em tela cheia (fullscreen)
- Impedir navegação fora do sistema
- Ocultar barras e elementos de interface
- Garantir experiência de uso dedicada ao sistema web

#### 2️⃣ Go Kiosk
**Função:**
- Bloquear o Android para uso exclusivo de um aplicativo
- Definir aplicativo de inicialização automática
- Impedir acesso ao launcher, configurações e outros apps

---

## 🔄 Funcionamento do Fluxo

1. O tablet é ligado ou reiniciado
2. O **Go Kiosk** inicia automaticamente
3. O Go Kiosk chama o **Fully Kiosk**
4. O Fully Kiosk abre o sistema **SCP em tela cheia**
5. Caso o usuário tente sair:
   - retorna automaticamente ao Fully
6. Nenhum outro aplicativo ou configuração fica acessível

---

## ✅ Resultado

- Sistema SCP disponível de forma dedicada
- Android totalmente restrito ao uso operacional
- Solução estável dentro das limitações impostas
- Excelente aceitação por parte da gerência
- Zero custo com licenças ou MDMs pagos

---

## 📎 Observações Importantes

- Esta solução **não substitui um MDM corporativo completo**
- Foi escolhida considerando:
  - custo zero
  - hardware disponível
  - limitações do ambiente
- Atende plenamente o cenário de uso operacional proposto

---

## 📷 Evidências

> *(Inserir imagens do tablet em uso no estaleiro / mockups ilustrativos)*

---

## 🧑‍💻 Autor

Projeto implementado e documentado por  
**Analista de Suporte / Infraestrutura**  
Estaleiro Mauá
