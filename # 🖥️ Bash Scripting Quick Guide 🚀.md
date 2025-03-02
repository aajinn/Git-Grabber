# 🖥️ Bash Scripting Quick Guide 🚀  

## 🔰 Basics  
```bash
#!/bin/bash  # 🏷️ Shebang - Defines the script interpreter  
echo "Hello, World! 🌍"  # 🗣️ Print to console  
```

## 📂 Variables  
```bash
name="Alice"  # 📌 Define a variable  
echo "Hello, $name! 👋"  # 🏷️ Use a variable  
```

## 📥 User Input  
```bash
read -p "Enter your name: " user_name  # 📩 Read user input  
echo "Welcome, $user_name! 🎉"  
```

## 📏 Conditional Statements  
```bash
num=10  
if [ $num -gt 5 ]; then  # ✅ If condition  
  echo "Number is greater than 5 🔼"  
elif [ $num -eq 5 ]; then  
  echo "Number is 5 🎯"  
else  
  echo "Number is less than 5 🔽"  
fi  
```

## 🔁 Loops  
```bash
# ➿ For loop  
for i in {1..5}; do  
  echo "Iteration: $i 🔄"  
done  

# 🔂 While loop  
count=1  
while [ $count -le 3 ]; do  
  echo "Count: $count ⏳"  
  ((count++))  
done  
```

## 🏗️ Functions  
```bash
say_hello() {  
  echo "Hello, $1! 🤗"  # 🎯 $1 is the first argument  
}  
say_hello "Alice"  
```

## 📂 File Operations  
```bash
touch file.txt  # 📄 Create a file  
echo "Hello, file! 📝" > file.txt  # 🖊️ Write to file  
cat file.txt  # 👀 Read file  
rm file.txt  # 🗑️ Delete file  
```

## 📜 Case Statements  
```bash
read -p "Enter a fruit: " fruit  
case $fruit in  
  apple) echo "🍎 Apple is red";;  
  banana) echo "🍌 Banana is yellow";;  
  orange) echo "🍊 Orange is orange";;  
  *) echo "Unknown fruit ❓";;  
esac  
```

## 🏗️ Arrays  
```bash
fruits=("🍎" "🍌" "🍊")  # 🍉 Define an array  
echo "First fruit: ${fruits[0]}"  # 🔢 Access element  
echo "All fruits: ${fruits[@]}"  # 🌍 Access all elements  
```

## 🖇️ Command Line Arguments  
```bash
echo "Script name: $0 📜"  # 🔍 Script name  
echo "First argument: $1 🎯"  # 🥇 First argument  
echo "All arguments: $@ 📦"  # 🗂️ All arguments  
```

## ⌛ Background Processes  
```bash
sleep 5 &  # 😴 Run in background  
jobs  # 🔎 List background jobs  
```

## 📊 Redirections & Pipes  
```bash
echo "Hello, file! 📄" > output.txt  # 🔀 Redirect output  
cat output.txt | grep "Hello"  # 🔍 Pipe output  
```

## 🔒 Permissions  
```bash
chmod +x script.sh  # 🛠️ Make script executable  
./script.sh  # ▶️ Run script  
```

## 🕵️ Process Management  
```bash
ps aux  # 👀 List running processes  
kill -9 PID  # ❌ Kill process  
```

## 🏁 Exit Status  
```bash
exit 0  # ✅ Successful exit  
exit 1  # ❌ Error exit  
```

Happy Scripting! 🎉🚀