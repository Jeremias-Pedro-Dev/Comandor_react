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
