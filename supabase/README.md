


<img width="2" height="3" alt="image" src="https://github.com/user-attachments/assets/b2ba03bf-cecf-4a45-81ba-16b3fbb1ab30" />


conect API URL

```
import { useState, useEffect } from 'react'
import { supabase } from '../utils/supabase'

export default function Page() {
  const [todos, setTodos] = useState([])

  useEffect(() => {
    async function getTodos() {
      const { data: todos } = await supabase.from('todos').select()

      if (todos) {
        setTodos(todos)
      }
    }

    getTodos()
  }, [])

  return (
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>{todo.name}</li>
      ))}
    </ul>
  )
}

```

