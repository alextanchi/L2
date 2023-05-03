Что выведет программа? Объяснить вывод программы. Рассказать про внутреннее устройство слайсов и что происходит при передачи их в качестве аргументов функции.

```go
package main

import (
	"fmt"
)

func main() {
	var s = []string{"1", "2", "3"}
	modifySlice(s)
	fmt.Println(s)
}

func modifySlice(i []string) {
	i[0] = "3"
	i = append(i, "4")
	i[1] = "5"
	i = append(i, "6")
}
```

Ответ:
```
Вывод: [3, 2, 3]
```
Последовательность отладки:
```
	Изначально длина и размер слайса 3, следовательно при изменении элемента с индексом 0, переданный в функцию слайс тоже изменится, ибо ссылка на базовый слайс такая-же.
	Но вот после того, как мы добавим элемент в переданный слайс, поля этого слайса тоже поменяются, следовательно указатель будет уже другой, и изменяться будет не базовый слайс, а уже локальный.
```