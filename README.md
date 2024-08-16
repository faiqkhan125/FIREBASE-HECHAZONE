<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="dashboard">
        <h1>Dashboard</h1>
        <div class="blog-form">
            <input type="text" placeholder="Placeholder" class="title-input" id="blog-title">
            <textarea placeholder="What is in your mind" class="content-input" id="blog-content"></textarea>
            <button class="publish-button" onclick="publishBlog()">Publish blog</button>
        </div>
        <h2>My Blogs</h2>
        <div class="blog-display" id="blog-display">
    
        </div>
    </div>

<script src="script.js"></script>
</body>
</html>



function publishBlog() {
    const title = document.getElementById('blog-title').value;
    const content = document.getElementById('blog-content').value;

    if (title && content) {
        const blogDisplay = document.getElementById('blog-display');
        
        const blogPost = document.createElement('div');
        blogPost.className = 'blog-post';
        blogPost.onclick = function() {
            window.location = 'profile.html';
        };

        const blogImage = document.createElement('img');
        blogImage.src = 'https://via.placeholder.com/50';
        
        const blogTitle = document.createElement('div');
        blogTitle.className = 'blog-title';
        blogTitle.textContent = title;
        
        const blogMeta = document.createElement('div');
        blogMeta.className = 'blog-meta';
        blogMeta.textContent = 'Author Name - ' + new Date().toLocaleDateString();

        const blogContent = document.createElement('div');
        blogContent.className = 'blog-content';
        blogContent.textContent = content;

        const blogActions = document.createElement('div');
        blogActions.className = 'blog-actions';
        
        const deleteButton = document.createElement('button');
        deleteButton.textContent = 'Delete';
        deleteButton.onclick = function() {
            blogPost.remove();
        };

        const editButton = document.createElement('button');
        editButton.textContent = 'Edit';
        editButton.style.marginLeft = '10px';
        editButton.onclick = function() {
            document.getElementById('blog-title').value = title;
            document.getElementById('blog-content').value = content;
            blogPost.remove();
        };

        blogActions.appendChild(deleteButton);
        blogActions.appendChild(editButton);
        
        blogPost.appendChild(blogImage);
        blogPost.appendChild(blogTitle);
        blogPost.appendChild(blogMeta);
        blogPost.appendChild(blogContent);
        blogPost.appendChild(blogActions);
        
        blogDisplay.appendChild(blogPost);

        document.getElementById('blog-title').value = '';
        document.getElementById('blog-content').value = '';
    } else {
        alert('Please fill out both the title and content fields.');
    }
}


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign In</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="profile-page">
        <h1>Sign In</h1>
        <form class="sign-in-form" onsubmit="return signIn()">
            <input type="text" id="username" placeholder="Username" required>
            <input type="email" id="email" placeholder="Email" required>
            <input type="password" id="password" placeholder="Password" required>
            <button type="submit">Sign In</button>
        </form>
    </div>

    <script src="profile.js"></script>
    
</body>
</html>



function signIn() {
    const username = document.getElementById('username').value;
    const email = document.getElementById('email').value;
    const password = document.getElementById('password').value;

    if (username && email && password) {
        alert(Welcome, $[username]);
        return false; 
    } else {
        alert('Please fill out all fields.');
        return false;
    }
}




body {
    font-family: Arial, sans-serif;
    background-color: #f8f9fa;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 200%;
    margin: 0;
}

.dashboard {
    width: 1000px;
    background-color: #eeebf3;
    justify-content: center;
    text-align: center;
    border-radius: 50px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding: 20px;
}

h1 {
    font-size: 24px;
    margin-bottom: 20px;
    text-align: center;

}

h2 {
    font-size: 20px;
    margin-bottom: 20px;
    margin-top: 30px;
}

.blog-form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-bottom: 20px;
}

.title-input, .content-input {
    width: 100%;
    padding: 10px;
    border: 2px solid #d7c2f0;
    border-radius: 4px;
    font-size: 16px;
}

.content-input {
    height: 100px;
    resize: none;
}

.publish-button {
    background-color: #6c5ce7;
    color: #ffffff;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
}

.publish-button:hover {
    background-color: #5942ba;
}

.blog-display {
    margin-top: 20px;
}

.blog-post {
    background-color: #f1f1f1;
    border-radius: 8px;
    padding: 15px;
    margin-bottom: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.blog-post img {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    float: left;
    margin-right: 15px;
}

.blog-title {
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 5px;
}

.blog-meta {
    color: #666;
    font-size: 14px;
    margin-bottom: 10px;
}

.blog-content {
    font-size: 16px;
    clear: both;
}

.blog-actions {
    margin-top: 10px;
}

.blog-actions button {
    background: none;
    border: none;
    color: #6c5ce7;
    cursor: pointer;
    font-size: 14px;
}

.blog-actions button:hover {
    text-decoration: underline;
}

.profile-page {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    flex-direction: column;
    background-color: #f8f9fa;
}

.sign-in-form {
    background-color: #ffffff;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.sign-in-form input {
    width: 100%;
    padding: 10px;
    border: 2px solid #d7c2f0;
    border-radius: 4px;
    font-size: 16px;
}

.sign-in-form button {
    background-color: #6c5ce7;
    color: #ffffff;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
}

.sign-in-form button:hover {
    background-color: #5942ba;
}








