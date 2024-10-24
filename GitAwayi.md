Haan, bilkul! GitHub ke initial setup ke liye main step-by-step guide deta hoon. Agar koi specific issue ho toh wo bhi bata dena. Chalo basic setup se shuru karte hain:

Step 1: Git Install Karna (Agar Installed Nahi Hai)

	1.	Git Download se apne OS ke liye download karo.
	2.	Install karne ke baad terminal ya command prompt pe git --version se check karo ki Git install ho gaya hai.

Step 2: GitHub Account Create Karna

	1.	GitHub pe jaake account create kar lo (Agar account already hai to is step ko skip kar do).

Step 3: Local Git Setup

git config --global user.name "Tumhara GitHub Username"
git config --global user.email "Tumhara Email Address (Jo GitHub pe registered hai)"

Ye command tumhara username aur email global settings mein store karega, taaki har commit pe author information rahe.

Step 4: New Repository Create Karna (GitHub Pe)

	1.	GitHub pe login karke New Repository button pe click karo.
	2.	Repository ka naam do aur README.md ko initialize karne ka option tick karo.
	3.	Create Repository pe click karo.

Step 5: Local Repository Ko GitHub Repository Se Link Karna

Agar Code Already Local Machine Par Hai:

cd project-folder  # Apne project folder mein jao
git init  # Git ko initialize karo
git add .  # Saare files ko stage pe le jao
git commit -m "Initial commit"  # Pehla commit karo

GitHub Repository Se Link:

git remote add origin https://github.com/username/repository-name.git
git branch -M main  # Default branch ko 'main' pe set karna (optional)
git push -u origin main  # Code GitHub pe push karo

Step 6: Agar Naya Code Directly Clone Karna Hai

git clone https://github.com/username/repository-name.git
cd repository-name

Step 7: Changes Push Karna (Daily Use Commands)

git add .  # Changes ko stage karo
git commit -m "Your message"  # Commit karo
git push origin main  # Changes ko GitHub pe push karo

Step 8: Agar Kisi Dusre Ka Repo Clone Karna Hai aur Kaam Karna Hai

	1.	Clone the repo:

git clone https://github.com/username/repository-name.git
cd repository-name


	2.	Apna branch banaake kaam karo:

git checkout -b new-feature  # Naya branch create karna


	3.	Kaam karke push karo:

git add .
git commit -m "Added new feature"
git push origin new-feature


	4.	Pull Request bana ke original repo pe review bhejo.

Agar koi specific doubt hai ya issue aa raha ho, to batao!