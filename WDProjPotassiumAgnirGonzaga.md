> AGNIR, Kacey Adelyne &
> GONZAGA, Germione Naj

**Website Title & Browser Tab Title:**
# cortado.io
Named after a Spanish espresso drink which is considered balanced, efficient, and energizing. It matches the essence of productivity--focus, clarity, and getting work done without excess. 


**Brief Description of the Website:**
A productivity and note-taking app for Grade 9 Pisay scholars. It is designed to make your academic experience organized and clean throughout the School Year.

**Logo Design Concept:**


# Website Outline:
This is the vision for our project: [Design](https://www.canva.com/design/DAG23alL040/XPYQeaERsiuzZ8fUottObQ/edit)

## Sign-in Page
* The webpage's background will have a **linear gradient** blending the colors of #997aaF and #ffcece. It will also contain **animated twinkling stars.** The stars will also contian a JavaScript code.
```
body{
    margin:0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(180deg, #997aaf, #ffcece);
    overflow: hidden;
    font-family: 'Comic Sans', 'Poppins', sans-serif;
}
.star{
    position: absolute;
    background: white;
    border-radius: 50%;
    opacity: 0;
    animation: twinkle 2s infinite ease-in-out;
}
@keyframes twinkle{
    0%, 100%{
        opacity: 0;
        transform: scale(1.05);
    } 
    50%{
        opacity: 1;
        transform: scale(1);
    }
}
```
* The user must complete the two input fields which are the **username** and **password**. Both fields **must** be completed for the user to log-in. 
* If the user hovers over the **log-in** button **without filling up the username and/or password**, the button will reposition itself, as if it is **running away** from the cursor. However if both fields are filled, the button will remain staitionary and clickable. This is one of the times where JavaScript will be incorporated.
```
    const numStars = 60;
    for (let i = 0; i < numStars; i++) {
        const star = document.createElement('div');
        star.classList.add('star');
        star.style.width = star.style.height = Math.random() * 3 + 'px';
        star.style.left = Math.random() * 100 + 'vw';
        star.style.top = Math.random() * 100 + 'vh';
        star.style.animationDelay = Math.random() * 2 + 's';
        document.body.appendChild(star);
    }
```
```
    const btn = document.getElementById('loginBtn');
    const username = document.getElementById('username');
    const password = document.getElementById('password');
    const buttonContainer = document.querySelector('.button-container');

    btn.addEventListener('mouseover', () => {
        if (username.value.trim() === '' || password.value.trim() === '') {
            const containerRect = buttonContainer.getBoundingClientRect();
            const btnWidth = btn.offsetWidth;
            const btnHeight = btn.offsetHeight;

            const x = Math.random() * (containerRect.width - btnWidth);
            const y = Math.random() * (containerRect.height - btnHeight);

            btn.style.left = `${x}px`;
            btn.style.top = `${y}px`;
            btn.style.transform = 'none';
        }
    });

    btn.addEventListener('click', () => {
        if (username.value.trim() && password.value.trim()) {
            alert(`Welcome, ${username.value}!`);
        }
    });
```
## Home/Main Page
1. NAVIGATION BAR   
* The side will contain a **navigation bar** on the **left side** and **on top** for **mobile**.
* Tabs: Dashboard, Subjects (limited to Grade 9), Calendar, Active Recall, Settings (Theme Toggle, Account, etc.). Some of these will require JavaScript.
#### On the left:
2. TO-DO LIST
* For the user to keep track of their progress. It will also contain a progress bar which will contain another JavaScript code
```
let progress=0;

function(increaseProgress){
    if(progress<100){
        progress+=10;
        document.getElementById('progress-bar').style.width=progress + '%';
    }
}
```
3. LINKS TO OTHER WEBSITES
* Located below the to-do list, the icons for each link will be **drawn** to fit the theme of our website. Once the user clicks on one app, they will be redirected to that website.

#### In the Middle:
4. WHITEBOARD
* Once the user clicks on the whiteboard, it will **expand**, covering the entire website which enables the user to **take notes**, **draw**, etc.

5. CALENDAR
* Sitting right below the whiteboard, 
. SPOTIFY AREA
* Includes a playlist of 3 (or more) different genres to choose from. It helps the user set the vibe for effective working.
