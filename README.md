<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>type X</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
    }
    header {
      background-color: #1877f2;
      color: white;
      padding: 10px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    header h1 {
      margin: 0;
      font-size: 24px;
    }
    header input {
      padding: 5px;
      border-radius: 5px;
      border: none;
    }
    .container {
      display: flex;
      margin: 20px;
    }
    .sidebar {
      width: 20%;
      background-color: white;
      padding: 15px;
      margin-right: 20px;
      border-radius: 10px;
      height: fit-content;
    }
    .feed {
      flex: 1;
    }
    .post-box {
      background-color: white;
      padding: 15px;
      margin-bottom: 20px;
      border-radius: 10px;
    }
    .post-box textarea {
      width: 100%;
      border-radius: 5px;
      padding: 10px;
      border: 1px solid #ccc;
      resize: none;
    }
    .post-box button {
      margin-top: 10px;
      padding: 8px 15px;
      border: none;
      background-color: #1877f2;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
    .post {
      background-color: white;
      padding: 15px;
      margin-bottom: 15px;
      border-radius: 10px;
    }
    .post h3 {
      margin: 0 0 5px 0;
    }
    .post p {
      margin: 5px 0 0 0;
    }
  </style>
</head>
<body>

  <header>
    <h1>type X</h1>
    <input type="text" placeholder="Search...">
  </header>

  <div class="container">
    <div class="sidebar">
      <h3>Menu</h3>
      <ul>
        <li>Home</li>
        <li>Profile</li>
        <li>Friends</li>
        <li>Messages</li>
      </ul>
    </div>

    <div class="feed">
      <div class="post-box">
        <textarea id="postContent" rows="3" placeholder="What's on your mind?"></textarea>
        <button onclick="addPost()">Post</button>
      </div>

      <div id="postsContainer">
        <!-- Posts will appear here -->
      </div>
    </div>
  </div>

  <script>
    function addPost() {
      const content = document.getElementById('postContent').value;
      if(content.trim() === "") return;

      const postContainer = document.getElementById('postsContainer');

      const postDiv = document.createElement('div');
      postDiv.className = 'post';
      postDiv.innerHTML = `
        <h3>User</h3>
        <p>${content}</p>
      `;

      postContainer.prepend(postDiv);
      document.getElementById('postContent').value = '';
    }
  </script>

</body>
</html>
