# MsDoors Addons - Sistema de Expansão Personalizável

> Bem-vindo aos Addons do **MsDoors**! Este repositório permite que você crie e gerencie addons personalizados para o MsDoors com facilidade. Personalize o jogo, adicione novas funcionalidades e tenha controle total sobre a experiência dos jogadores! 🎮✨

---

## 📥 Instalação

1. **Vá para o [Repositório do Msdoors](https://github.com/Sc-Rhyan57/Msdoors) e copie e execute o script em seu executor.**
2. **Baixe um aplicativo como [ZarChiver](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver) ou [Gerenciador de Arquivos+](https://play.google.com/store/apps/details?id=com.alphainventor.filemanager), depois de baixar vá para as configurações de algum dos aplicativos selecionado por você e ative a opção "**__VER ARQUIVOS OCULTOS__**" depois disso vá para **Armazenamento Principal/{Pasta do seu Executor}/.msdoors/addons**.

3. **Adicione Addons** copiando arquivos `.lua` para a pasta `.Msdoors/addons`. O script do MsDoors detectará e carregará automaticamente esses addons quando o jogo for iniciado!

> [!IMPORTANT]
> Caso não esteja conseguindo usar essa função entre em contato comigo pelo [Discord](https://dsc.gg/BetterStar)!
---

## 🔧 Estrutura de um Addon

Cada addon deve ser um arquivo `.lua` com uma estrutura básica, incluindo **nome**, **título**, **descrição** e **elementos**.

### Estrutura Básica do Addon

```lua
return {
    Name = "NomeDoAddon",  -- Nome interno do addon
    Title = "Título Exibido",  -- Título mostrado na interface
    Description = "Descrição do que o addon faz",  -- Explicação sobre o addon
    Elements = {  -- Elementos de UI para o addon
        -- Defina aqui os elementos do addon
    }
}
```

### Exemplo Simples

```lua
return {
    Name = "ExemploAddon",
    Title = "Meu Addon de Exemplo",
    Description = "Esse addon é um exemplo básico para o sistema MsDoors.",
    Elements = {
        {
            Type = "Label",
            Name = "ExemploLabel",
            Arguments = { "Bem-vindo ao meu addon!" }
        },
        {
            Type = "Button",
            Name = "ExemploBotao",
            Arguments = {
                Name = "Clique Aqui",
                Callback = function()
                    print("Botão foi clicado!")
                end
            }
        }
    }
}
```

---

## 🌐 Lista Completa de Recursos

Aqui está uma visão geral dos recursos disponíveis para os addons MsDoors.

### 📋 Tipos de Elementos Disponíveis

| Tipo de Elemento | Descrição                                    | Exemplo de Uso                                                                                       |
|------------------|----------------------------------------------|------------------------------------------------------------------------------------------------------|
| `Label`          | Exibe um texto fixo na interface             | `{ Type = "Label", Name = "BemVindoLabel", Arguments = { "Bem-vindo!" } }`                           |
| `Toggle`         | Botão liga/desliga                           | `{ Type = "Toggle", Name = "AtivarFuncao", Arguments = { Default = true, Callback = function(val) ... end } }` |
| `Button`         | Botão clicável                               | `{ Type = "Button", Name = "BotaoExemplo", Arguments = { Name = "Clique Aqui", Callback = function() ... end } }` |
| `Slider`         | Controle deslizante                          | `{ Type = "Slider", Name = "Volume", Arguments = { Min = 0, Max = 100, Default = 50, Callback = function(val) ... end } }` |
| `Input`          | Campo de entrada de texto                    | `{ Type = "Input", Name = "NomeJogador", Arguments = { Default = "Digite seu nome", Callback = function(text) ... end } }` |
| `Dropdown`       | Lista suspensa                               | `{ Type = "Dropdown", Name = "OpcoesExemplo", Arguments = { Options = {"Opção1", "Opção2"}, Callback = function(val) ... end } }` |
| `ColorPicker`    | Seletor de cor                               | `{ Type = "ColorPicker", Name = "CorPreferida", Arguments = { Default = Color3.new(1, 0, 0), Callback = function(color) ... end } }` |
| `KeyPicker`      | Seletor de tecla para atalhos                | `{ Type = "KeyPicker", Name = "TeclaAtalho", Arguments = { Default = Enum.KeyCode.F, Callback = function(key) ... end } }` |

---

## 🎨 Personalização de Interface

Abaixo estão as principais opções de personalização de interface que podem ser aplicadas nos elementos dos addons:

- **Cores Customizáveis**: Defina cores para o fundo, bordas e texto dos elementos. O seletor de cor (`ColorPicker`) permite ajustar cores em RGB.
- **Opacidade e Transparência**: Ajuste a opacidade dos elementos para um visual mais sutil ou proeminente.
- **Posições Customizáveis**: Controle a posição dos elementos com propriedades como `AnchorPoint`, `Position` e `Size`.
  
### Exemplo de Configuração de Cor e Opacidade

```lua
{
    Type = "ColorPicker",
    Name = "CorPersonalizada",
    Arguments = {
        Default = Color3.fromRGB(255, 100, 100),  -- Cor padrão
        Callback = function(corSelecionada)
            print("Cor selecionada:", corSelecionada)
        end
    }
}
```

## 📑 Recursos Avançados e Funcionalidades

Os addons de MsDoors suportam funcionalidades avançadas e opções de personalização que ampliam o potencial da experiência. Aqui estão alguns exemplos de funções adicionais que podem ser usadas nos addons:


### 🎮 Configurações de Controles e Atalhos

Implemente controles personalizados com `KeyPicker`, permitindo que jogadores definam teclas para acessar funcionalidades específicas:

```lua
{
    Type = "KeyPicker",
    Name = "AtalhoEspecial",
    Arguments = {
        Default = Enum.KeyCode.G,
        Callback = function(teclaPressionada)
            print("Tecla pressionada:", teclaPressionada)
        end
    }
}
```

---

## 🛠️ Exemplo Completo de Addon Personalizado

Aqui está um exemplo completo de addon para personalizar notificações e controlar aspectos de interface:

```lua
return {
    Name = "PersonalizacaoExemplo",
    Title = "Addon Personalizável",
    Description = "Um addon que permite ajustar cores, opacidade e exibir notificações.",
    Elements = {
        {
            Type = "ColorPicker",
            Name = "CorFundo",
            Arguments = {
                Default = Color3.new(1, 1, 1),
                Callback = function(cor)
                    print("Cor do fundo alterada para:", cor)
                end
            }
        },
        {
            Type = "Slider",
            Name = "Opacidade",
            Arguments = {
                Min = 0,
                Max = 100,
                Default = 100,
                Callback = function(valor)
                    print("Opacidade definida para:", valor)
                end
            }
        },
        {
            Type = "Button",
            Name = "EnviarNotificacao",
            Arguments = {


                Name = "Notificar",
                Callback = function()
                    MsdoorsNotify(
                        "Alerta Importante", 
                        "Verifique a nova configuração!", 
                        "Aviso",
                        "rbxassetid://6023426923",
                        Color3.new(1, 0, 0), 
                        5
                    )
                end
            }
        }
    }
}
```
