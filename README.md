# Comandor_react
 
# @react-native-community/datetimepicker

## Instalação (Expo)

```bash
npx expo install @react-native-community/datetimepicker
```

## Importação

```javascript
import DateTimePicker from "@react-native-community/datetimepicker";
```

---

# O que é?

O `@react-native-community/datetimepicker` é uma biblioteca que permite exibir o seletor nativo de **data** e **hora** do Android e do iOS.

Em vez de o usuário digitar uma data manualmente, ele escolhe através do calendário ou do relógio do próprio sistema operacional.

---

# Para que serve?

É utilizado para:

* Selecionar data de nascimento.
* Selecionar horário.
* Agendar consultas.
* Marcar reuniões.
* Criar lembretes.
* Escolher a data de um evento.
* Registrar datas em formulários.
* Selecionar a data em aplicativos de pessoas desaparecidas.
* Escolher data e hora de publicações.

---

# Comando de uso

## Data

```jsx
<DateTimePicker
  value={new Date()}
  mode="date"
  display="default"
  onChange={onChange}
/>
```

---

## Hora

```jsx
<DateTimePicker
  value={new Date()}
  mode="time"
  display="default"
  onChange={onChange}
/>
```

---

## Data e Hora

```jsx
<DateTimePicker
  value={new Date()}
  mode="datetime"
  display="default"
  onChange={onChange}
/>
```

> **Observação:** O modo `datetime` pode não estar disponível da mesma forma em todas as plataformas. Em Android, normalmente utiliza-se `date` e `time` separadamente.

---

# Principais propriedades

| Propriedade | Função                                                            |
| ----------- | ----------------------------------------------------------------- |
| `value`     | Data ou hora inicial.                                             |
| `mode`      | Define o tipo (`date`, `time` ou `datetime`).                     |
| `display`   | Tipo de visualização (`default`, `spinner`, `calendar`, `clock`). |
| `onChange`  | Executado quando o usuário escolhe uma data ou hora.              |

---

# Exemplo completo

```jsx
import React, { useState } from "react";
import { View, Button } from "react-native";
import DateTimePicker from "@react-native-community/datetimepicker";

export default function App() {
  const [date, setDate] = useState(new Date());
  const [show, setShow] = useState(false);

  const onChange = (event, selectedDate) => {
    setShow(false);

    if (selectedDate) {
      setDate(selectedDate);
    }
  };

  return (
    <View>
      <Button
        title="Selecionar Data"
        onPress={() => setShow(true)}
      />

      {show && (
        <DateTimePicker
          value={date}
          mode="date"
          display="default"
          onChange={onChange}
        />
      )}
    </View>
  );
}
```

---

# Resumo

✅ Instala o seletor nativo de data e hora.

✅ Funciona no Android e iOS.

✅ Ideal para formulários, cadastros, agendamentos, eventos e qualquer situação em que o usuário precise escolher uma data ou horário.

# ScrollView Horizontal no React Native

## O que é?

O `ScrollView` é um componente do React Native utilizado para exibir conteúdo rolável (scroll). Ele pode rolar na vertical ou na horizontal.

Importação:

```javascript
import { ScrollView } from "react-native";
```

---

# Exemplo

```jsx
<ScrollView
  horizontal
  showsHorizontalScrollIndicator={false}
  style={styles.servicesScroll}
  contentContainerStyle={styles.servicesScrollContent}
>
  {/* Conteúdo */}
</ScrollView>
```

---

# Explicação de cada propriedade

## `horizontal`

```jsx
horizontal
```

Define que o `ScrollView` deve rolar na horizontal.

Sem essa propriedade, a rolagem será vertical por padrão.

### Vertical (padrão)

```
Item
Item
Item
Item
```

↓

### Horizontal

```
Item   Item   Item   Item
```

← →

---

## `showsHorizontalScrollIndicator={false}`

```jsx
showsHorizontalScrollIndicator={false}
```

Controla a barra de rolagem horizontal.

### `true`

Mostra a barra de rolagem.

```
──────────────────────────
██████████████
```

### `false`

Esconde a barra de rolagem, deixando a interface mais limpa.

É muito utilizada em listas de cartões, produtos, médicos, categorias e serviços.

---

## `style={styles.servicesScroll}`

```jsx
style={styles.servicesScroll}
```

Aplica estilos ao próprio componente `ScrollView`.

Exemplo:

```javascript
servicesScroll: {
  paddingHorizontal: 24,
}
```

Pode ser usado para definir:

* margem (`margin`)
* preenchimento (`padding`)
* largura (`width`)
* altura (`height`)
* cor de fundo (`backgroundColor`)
* entre outros estilos do contêiner.

---

## `contentContainerStyle={styles.servicesScrollContent}`

```jsx
contentContainerStyle={styles.servicesScrollContent}
```

Aplica estilos ao conteúdo interno do `ScrollView`, e não ao componente externo.

Exemplo:

```javascript
servicesScrollContent: {
  gap: 16,
  paddingRight: 24,
}
```

### `gap`

Cria espaço entre os itens.

```
[Card]   16px   [Card]   16px   [Card]
```

### `paddingRight`

Adiciona espaço no final da lista para que o último item não fique colado na borda da tela.

---

# Diferença entre `style` e `contentContainerStyle`

## `style`

Estiliza o contêiner do `ScrollView`.

```
┌──────────────────────────────┐
│        ScrollView            │
│                              │
│  Conteúdo                    │
└──────────────────────────────┘
```

---

## `contentContainerStyle`

Estiliza apenas os elementos que ficam dentro do `ScrollView`.

```
┌──────────────────────────────┐
│ ScrollView                   │
│ ┌──────────────────────────┐ │
│ │ Item  Item  Item  Item   │ │
│ └──────────────────────────┘ │
└──────────────────────────────┘
```

---

# Quando usar um ScrollView horizontal?

Use quando deseja criar listas que o usuário percorre deslizando para os lados, como:

* Lista de médicos.
* Lista de serviços.
* Categorias.
* Produtos.
* Restaurantes.
* Notícias.
* Imagens.
* Cartões de crédito.
* Filmes e séries.

---

# Resumo

| Propriedade                              | Função                                      |
| ---------------------------------------- | ------------------------------------------- |
| `horizontal`                             | Ativa a rolagem horizontal.                 |
| `showsHorizontalScrollIndicator={false}` | Oculta a barra de rolagem horizontal.       |
| `style`                                  | Estiliza o contêiner do `ScrollView`.       |
| `contentContainerStyle`                  | Estiliza os itens internos do `ScrollView`. |

---

# Estrutura completa

```jsx
<ScrollView
  horizontal
  showsHorizontalScrollIndicator={false}
  style={styles.servicesScroll}
  contentContainerStyle={styles.servicesScrollContent}
>
  {/* Seus componentes aqui */}
</ScrollView>
```

