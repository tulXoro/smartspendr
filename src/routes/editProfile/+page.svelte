<script>
    // @ts-nocheck
        import BackArrow from '../../lib/BackArrow.svelte';
        import profilePic from '$lib/profilePic.png';
        
        let uploaded = false;
        let username = "John Doe";
        let email = "JohnDoe@gmail.com";
        let password = "•••••••";
        let saved = false;
        let newImg;
    
        function handleSave() {
            saved = true;
        }

        const uploadFile = (/** @type {Event & { currentTarget: EventTarget & HTMLInputElement; }} */ e) => {
            uploaded = true;
            
            if (e.target != null){
                let image = e.target.files[0];
                let reader = new FileReader();
                reader.readAsDataURL(image);
                reader.onload = e => {
                    if (e.target != null){
                        newImg = e.target.result
                    }
                };
            }
            
        };
    </script>
    
    <style>
        .button{
            cursor: pointer;
            border-radius: 6px;
            padding: 8px 12px;
            font-weight: bold;
            box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
            font-size: 26px;
            margin-top: 20px;
            display: flex; 
            width: auto;
            height: auto;
            background: #2563EB;
            color: white;
            align-items: center; 
            justify-content: center; 
            width: 30vw;
        }
        .form{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 30px;
        }
        .input{
            width: 100%;
            height: 8vh;
            padding: 12px;
            margin: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            background-color: rgb(222, 236, 255);
            margin-bottom: 24px;
        }
        .img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 20px;
            overflow: hidden;
        }
        img {
            max-width: 100%;    
        }
        .imgdiv {
            display: flex;
            flex-direction: column;
            justify-content: start;
            align-items: center;
            margin-bottom: 40px;
        }
        .uploadImg {
            display: none;
        }
        .label {
            cursor: pointer;
            border-radius: 6px;
            font-weight: bold;
            box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
            background-color: #E53E3E;
            padding: 10px;
            width: auto;
            color: white;
        }
        h1 {
            font-size: xx-large;
            font-weight: 900;
        }
        .inputLabels {
            margin-left: 10px;
            color: #808080;
        }
        .outer {
            margin: auto;
            margin-top: 30px;
            border: 1px solid #808080;
            border-radius: 9px;
            padding: 25px;
            box-shadow: 10px 15px 5px  #d6d6d6;
            width: 90%;
        }
    </style>
   
<div class="outer">
    <BackArrow />
    <form class="form">
        <div class="imgdiv">
            <h1>@JohnDoe</h1>
            <div class="img">
                {#if uploaded}
                    <!-- svelte-ignore a11y-img-redundant-alt -->
                    <img src={newImg} alt="uploaded image"/>
                {:else}
                    <img id="profilePic" src={profilePic} alt="blank profile pic" />
                {/if}
            </div>
            <label class="label" for="uploadButton">Upload Image</label>
            <input class="uploadImg" type="file" accept=".jpg, .jpeg, .png" on:change={(e)=>uploadFile(e)} id="uploadButton" >
        </div>
        <div class="info">
            <label class="inputLabels" for="username">Your Username</label>
            <input id="username" class="input" type="text" placeholder="Username" bind:value={username}>
            <label class="inputLabels" for="email">Your Email</label>
            <input id="email" class="input" type="text" placeholder="Email" bind:value={email}>
            <label class="inputLabels" for="password">Your Password</label>
            <input id="password" class="input" type="password" placeholder="Password" bind:value={password}>
        </div>
        {#if saved}
            <button class="button">Saved!</button>
        {:else}
            <button on:click={handleSave} class="button">Save Profile</button>
        {/if}
    </form>
</div>