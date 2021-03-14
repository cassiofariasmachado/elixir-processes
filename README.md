# Elixir processes

Notes about the Elixir processes.

## Creating a process

```elixir
pid = spawn fn -> IO.puts("hello world") end
```

## Checking if a process is alive

```elixir
Process.alive?(pid)
```

## Getting current process

```elixir
pid = self()
```

## Sending messages to process

```elixir
send pid, {:ok, "Mensagem de sucesso"}
```

## Receiving messages inside a process

```elixir
receive do
    {:ok, message} -> message
    {:error, _reason} -> "Deu ruim"
end
```

## Spawn a process that send message

```elixir
spawn fn -> send pid, {:ok, "Mensagem de sucesso"} end
```