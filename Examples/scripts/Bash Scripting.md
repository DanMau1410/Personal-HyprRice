# Create a Bash script
```
touch hello_world.sh
```
# Make it executable
```
chmod +x hello_world.sh
```
# Now edit it with your preferred text editor
```
nvim hello_world.sh
```

---
## Variables
```
name="James"
echo "$name"
```

Remember to quote any variables to prevent unwanted behavior

## Conditionals
```
name="Dylan"

if [[ $name == "Dylan" ]]; then
	echo "hello dylan"
elif [[ $name == "Bob" ]]; then
	echo "hello bob"
else
	echo "hello user"
fi
```

The `[[ ]]` syntax is Bash-specific. It allows you to use Regex and you don't have to quote variables to prevent word splitting. If you want to, however, be a good programmer, use POSIX-compliant *\[]* for if statements.

## For loop
```
for (( i = 0; i < 10; i++ )); do
	echo "$i"
done
```

This is the loop syntax you're probably already familiar with. Use this because it's simple.

## While loop
```
i=0

while [ $i -le 10 ]; do
	echo "$i"
done
```

**Did you know?** We always leave a space after the first bracket (\[) because the bracket stands for a command called `test`. Yes, literally. Type the `man test` and you can read the manual for it.

## Math
```
x=10
y=20

sum=$((x + y))

echo "$sum"
```

We quote variables to make sure that no word splitting occurs. *Don't want your words to be all chopped up :)*

## Functions
```
function say_hello() {
	echo "hello my friend"
}

say_hello
say_hello
say_hello
```

If you've written Java or Python before and want to replicate the main method:
```
function main() {
	function say_hello() {
		echo "hello my friend i am inside main"
	}
	
	say_hello
}

main
```

## Command-line args
`$0` is the program name
`$1` is the first argument
`$2` is the second argument and so on

`echo "$0 $1 $2"` would print out the first, second and third argument on the screen.

So `./hello_world.sh` would print
```
❯ ./hello_world.sh hello friend
./hello_world.sh hello friend
```

```
❯ ./hello_world.sh hello friend world
./hello_world.sh hello friend
```
Does not print `world` as we haven't asked it to print the 4th argument.