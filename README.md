# 🏥 Gestão Clínica - Fisioterapia & Podologia

![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

Um sistema completo (CRM + Landing Page) para gestão de clínicas, desenvolvido para otimizar o tempo de profissionais da saúde. O projeto conta com agendamento online pelo paciente, integração em tempo real e sincronização automática com o Google Calendar.

> 🔗 **Acesse o projeto online:** https://juliacruzsaude.vercel.app/

---

## 📸 Demonstração

<div align="center">
 
  **Tela de Login**
  <img width="1910" height="908" alt="Login Screan" src="https://github.com/user-attachments/assets/a44b9fe5-08e9-4cd2-b00c-91c2c9f83c1d" />
  
  **Visão Geral do Google**
  <img width="1910" height="908" alt="Visão Geral do Google" src="https://github.com/user-attachments/assets/9f28c9ca-c14f-464e-84fe-a34132a24299" />
  
  **Visão Clínica**
  <img width="1910" height="908" alt="Visão Clínica" src="https://github.com/user-attachments/assets/da371509-1016-4f66-aec4-9911c9ebeeed" />
  
  **Novo Agendamento**
  <img width="1911" height="909" alt="image" src="https://github.com/user-attachments/assets/6cf663ed-9483-4f16-b370-b1b45f2b9554" />
  
  **Cadastro de Paciente**
  <img width="1902" height="906" alt="image" src="https://github.com/user-attachments/assets/6c7323b5-418e-4cb2-8446-c01ab7611abf" />
  
  **Prontuários**
  <img width="1903" height="913" alt="image" src="https://github.com/user-attachments/assets/f460a2c5-5488-499a-9c8a-d96d1efb82b3" />
  
  **Prontuários Aberto**
  <img width="1909" height="911" alt="image" src="https://github.com/user-attachments/assets/e0dd2fd7-c8b4-419e-806a-4193c5aca8f5" />
  
</div>

---

## 🎯 O Problema Resolvido

Muitos profissionais da saúde perdem horas organizando agendas no papel ou WhatsApp, além de terem prontuários espalhados. Este sistema resolve isso em duas frentes:
1. **Para o Paciente:** Uma Landing Page elegante, responsiva (mobile-first) onde ele mesmo escolhe o dia e horário, respeitando regras de negócio (sem domingos/feriados e bloqueio de horários já ocupados).
2. **Para a Profissional:** Um painel administrativo (CRM) protegido por login para gerenciar prontuários, adicionar evoluções com fotos e visualizar a agenda unificada.

## ✨ Principais Funcionalidades

* **Auto-Agendamento:** Pacientes marcam consultas diretamente pelo site. O sistema faz a validação para evitar choques de horário.
* **Sincronização Bidirecional:** Qualquer agendamento criado, editado ou cancelado no CRM reflete instantaneamente no **Google Calendar** da profissional, com cores separadas por especialidade (Amarelo para Fisioterapia, Roxo para Podologia).
* **Supabase Realtime:** Atualização instantânea da tela do CRM quando um paciente agenda pelo site público, sem precisar atualizar a página (WebSockets).
* **Gestão de Prontuários:** Cadastro completo de pacientes via API de CEP (ViaCEP) e histórico de evoluções clínicas com upload de imagens.
* **Redirecionamento Inteligente:** Botões geram links dinâmicos para confirmação de consultas direto no WhatsApp do paciente.

---

## 🛠️ Tecnologias Utilizadas

**Front-end:**
* React (Vite)
* Tailwind CSS + Framer Motion (para animações fluidas)
* Lucide React (Ícones)
* Hospedagem: Vercel

**Back-end & Banco de Dados:**
* Node.js com Express
* Supabase (PostgreSQL + Storage de Imagens + Realtime/WebSockets)
* Googleapis (Integração OAuth2 para manipular a agenda debaixo dos panos)
* Hospedagem: Render

---

## ⚙️ Arquitetura do Sistema

O fluxo principal de agendamento funciona da seguinte forma:
1. O Front-end envia uma requisição `POST` para o servidor Node.js com os dados do paciente.
2. O servidor valida se o horário está disponível no Supabase.
3. Estando livre, salva os dados no Supabase.
4. O servidor utiliza o `refresh_token` armazenado para se autenticar silenciosamente na API do Google Calendar e cria o evento.
5. O ID do evento no Google é salvo de volta no Supabase para permitir futuras edições ou cancelamentos.
6. O Supabase dispara um evento *Realtime* para o front-end, que atualiza a interface gráfica automaticamente.

---

---

## 👨‍💻 Autor

**Christian Duarte** Graduando em Ciência da Computação (5º período) pela Universidade Anhanguera. Desenvolvi este sistema full-stack do zero para resolver uma dor real de negócios, aplicando na prática meus conhecimentos em arquitetura de software, integração de APIs e banco de dados. 

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/christianduart)
