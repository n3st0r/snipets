# Bash loops
[README.md - back](../README.md)

## Basic for loop
```bash
for file in /boot/*; do
  ls "$file"
done
```
One liner version
```bash
for file in /boot/*; do ls $file; done
```

## C-like for loop
```bash
for ((i = 0 ; i < 100 ; i++)); do
  echo "$i"
done
```

## Ranges
```bash
for num in {1..9}; do
    echo "Welcome $num"
done
```
One liner version
```bash
for num in {0..9}; do echo $num; done
```

## With step size
```bash
for i in {5..50..5}; do
    echo "Welcome $i"
done
```

## Reading lines
```bash
while read -r line; do
  echo "$line"
done <file.txt
```

## Forever
```bash
while true; do
  ···
done
```

## Loop by list
```bash
for item in $(echo foo bar baz); do echo $item; done
```
