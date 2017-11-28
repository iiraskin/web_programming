package main

import (
	"unicode"
	"strings"
)


func RemoveEven(array []int) []int {
	new_array := make([]int, 0)
	for i := 0; i < len(array); i++ {
	    if array[i] % 2 == 1 {
	    	new_array = append(new_array, array[i])
	    }
	}
	return new_array
}

func PowerGenerator(num int) func() int{
	res := 1
	return func() int {
	    res *= num
	    return  res
	}
}

func DifferentWordsCount(a string) int {
	res := make(map[string]int);
	temp := ""
	for _, word:= range a {
		wor := rune(word)
		if unicode.IsLetter(wor) {
			temp += string(word)
		} else if len(temp) > 0 {
			res[strings.ToUpper(temp)] = 1
			temp = ""
		}
	}

	if len(temp) > 0 {
		res[strings.ToUpper(temp)] = 1
	}

	return len(res)
}