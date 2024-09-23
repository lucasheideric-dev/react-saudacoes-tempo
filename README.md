# Saudações Horárias em React

![Projeto em execução](https://imgur.com/3MoU3Lk.png)

Este é um projeto simples em React que exibe a hora atual e saúda o usuário com "Bom dia", "Boa tarde" ou "Boa noite", dependendo do horário.

## Funcionalidades

- Exibe a hora atual atualizada em tempo real.
- Saudação dinâmica com base na hora:
  - **Bom dia**: antes das 12h.
  - **Boa tarde**: entre 12h e 18h.
  - **Boa noite**: após 18h.

## Como Funciona

O projeto utiliza o `useState` e o `useEffect` do React para capturar a hora atual e atualizar a saudação automaticamente conforme a mudança de tempo.

### Código do Componente

Abaixo está o código do componente principal:

```javascript
const Page = () => {
  const fullTime = new Intl.DateTimeFormat('pt-BR', { timeStyle: 'short', hour12: false }).format();
  const hour = new Date().getHours();
  let greeting = '';

  if (hour >= 0 && hour < 12) {
    greeting = 'Bom dia';
  } else if (hour >= 12 && hour < 18) {
    greeting = 'Boa tarde';
  } else if (hour >= 18 && hour < 23) {
    greeting = 'Boa noite';
  }

  return (
    <div className="w-screen h-screen flex flex-col justify-center items-center bg-gradient-to-r from-sky-500 to-indigo-500">
      <div className="text-9xl text-white font-bold">{fullTime}</div>
      <div className="text-5xl text-yellow-300">- {greeting}</div>
    </div>
  );
}

export default Page;
