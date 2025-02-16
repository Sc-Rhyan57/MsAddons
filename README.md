### 📖 Documentação - Sistema de Addons para MsDoors
> Bem-vindo à documentação oficial do sistema de addons do **MsDoors**! Aqui você aprenderá como adicionar novos elementos, criar seus próprios addons e utilizar as funcionalidades disponíveis.

> [!NOTE]
> Nosso site tutorial para adição de Addons está disponível!
> [Msdoors/Addons](https://msdoors-gg.vercel.app/Addons)
---

## 🚀 Introdução
O sistema de addons do **MsDoors** permite que os jogadores adicionem e personalizem elementos dentro do jogo, utilizando scripts externos armazenados na pasta `msdoors/addons`.

> [!NOTE]
> Qualquer script colocado na pasta `msdoors/addons` e que siga o formato correto será carregado automaticamente no jogo.

---

## 📂 Estrutura da Pasta

Para garantir o funcionamento correto do sistema de addons, a estrutura de pastas deve ser a seguinte:

```
msdoors/
│── addons/
│   ├── meu_addon.lua
│   ├── outro_addon.luau
```

[!WARN]
> Apenas arquivos `.lua`, `.luau` e `.txt` são carregados pelo sistema.

---

## 🛠️ Como Criar um Addon

Os addons são scripts que seguem um formato específico. Aqui está um exemplo de como criar um addon:

```lua
return {
    Name = "Exemplo de Addon",
    Description = "Este é um addon de exemplo!",
    Elements = {
        {
            Type = "Label",
            Arguments = { Text = "Este é um rótulo de exemplo!" }
        },
        {
            Type = "Button",
            Arguments = { Text = "Clique aqui!", Callback = function() print("Botão pressionado!") end }
        }
    }
}
```

Cada addon deve retornar uma tabela com as seguintes chaves:

| Campo       | Tipo    | Descrição |
|------------|--------|------------|
| `Name`      | string | Nome do addon |
| `Description` | string | Breve descrição do addon |
| `Elements`  | table  | Lista de elementos que serão adicionados |

---

## 🔹 Tipos de Elementos Suportados

Os addons podem conter diferentes tipos de elementos na interface. Aqui está uma lista dos elementos suportados:

| Tipo         | Descrição |
|--------------|------------|
| `Divider`    | Adiciona um divisor|
| `Label`      | Adiciona um rótulo de texto |
| `Toggle`     | Adiciona uma opção ativar/desativar |
| `Button`     | Adiciona um botão clicável |
| `Slider`     | Adiciona um controle deslizante |
| `Input`      | Adiciona uma caixa de entrada de texto |
| `Dropdown`   | Adiciona uma lista suspensa |
| `ColorPicker`| Adiciona um seletor de cor |
| `KeyPicker`  | Adiciona um seletor de tecla |

Cada tipo de elemento possui argumentos específicos que devem ser passados na chave `Arguments`.

---

## 🎨 Exemplo Avançado

Aqui está um exemplo mais avançado de um addon que inclui diferentes elementos:

```lua
return {
    Name = "Ferramentas de Desenvolvedor",
    Description = "Vários utilitários para desenvolvedores!",
    Elements = {
        {
            Type = "Label",
            Arguments = { Text = "Configurações Gerais" }
        },
        {
            Type = "Toggle",
            Name = "modo_debug",
            Arguments = { Text = "Modo Debug", Default = false, Callback = function(state) print("Debug: ", state) end }
        },
        {
            Type = "Slider",
            Name = "velocidade",
            Arguments = { Text = "Velocidade", Min = 1, Max = 10, Default = 5, Callback = function(value) print("Velocidade ajustada para: ", value) end }
        }
    }
}
```

---

## 🔄 Como Carregar Novos Addons

Depois de adicionar um novo addon na pasta `msdoors/addons`, reinicie o script para que ele seja carregado automaticamente. Se houver algum erro, ele será exibido no console.

> [!TIP]
> Certifique-se de que seu addon segue o formato correto para evitar erros.

---

## 🛑 Erros Comuns

Aqui estão alguns erros comuns e como resolvê-los:

| Erro | Causa | Solução |
|------|-------|---------|
| `Elemento inválido` | Tipo de elemento incorreto | Verifique se o tipo do elemento está correto |
| `Erro ao carregar addon` | Sintaxe incorreta no arquivo | Corrija os erros no código do addon |
| `Pasta 'msdoors/addons' está vazia` | Nenhum addon foi encontrado | Adicione um arquivo de addon e reinicie o script |

---

## 🎯 Conclusão

Agora você sabe como adicionar novos elementos, criar addons personalizados e carregar suas modificações no **MsDoors**! Se tiver dúvidas, verifique os exemplos acima e certifique-se de seguir a estrutura correta.

> [!IMPORTANT]
> Viu o Tutorial e do mesmo jeito não consgeue adcionar addons ao seu executor? acesse nosso [Discord](https://dsc.gg/Msdoors-gg) para que possamos te ajudar.


> [!NOTE]
> Divirta-se criando seus próprios addons e personalizando sua experiência no jogo! 🚀
