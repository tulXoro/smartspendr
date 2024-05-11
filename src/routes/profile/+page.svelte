<script>
    // @ts-nocheck
        import rightArrow from '$lib/rightArrow.png';
        import editProfile from '$lib/editProfile.png';
        import bell from '$lib/bell.png';
        import creditCard from '$lib/credit-card.png';
        import subscription from '$lib/subscription.png';
        import profilePic from '$lib/profilePic.png';
        
        let uploaded = false;
        let username = "John Doe";
        let email = "JohnDoe@gmail.com";
        let newImg;
    
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
            width: 90%;
            height: 8vh;
            padding: 12px;
            margin: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            background-color: rgb(224, 231, 240);
            margin-bottom: 20px;
        }
        img {
            max-width: 100%; 
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;   
        }
        .imgdiv {
            display: flex;
            flex-direction: column;
            justify-content: start;
            align-items: center;
            margin-bottom: 40px;
            border-bottom: 1px solid #bcbcbc;
        }
        h1 {
            font-size: xx-large;
            font-weight: 900;
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
        p {
            margin-bottom: 10px;
        }
        li {
            
            height: 9vh;
            padding: 13px;
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #bcbcbc;
        }
        .arrow {
            height: 4vh;
            width: 3vw;
            margin-top: auto;
        }
        .icon {
            height: 35px;
            width: 35px;
            margin-top: auto;
            margin-bottom: auto;
            margin-right: 10px;
        }
        .title {
            display: flex;
            flex-direction: row;
        }
        .labels {
            font-size: 2.8vh;
            margin: auto;
        }
    </style>
    
    <div class="outer">
        <div class="imgdiv">
            <img id="uploadButton" src={profilePic} alt="blank profile pic" />
            <h1>John Doe</h1>
            <p>jDoe@gmail.com</p>
        </div>
        <ul>
            <a href="/editProfile">
            <li>
                <div class="title">
                    <img class="icon" src={editProfile} alt="profileIcon"/>
                    <p class="labels">Edit Profile</p>
                </div> 
                <img class="arrow" src={rightArrow} alt="arrow"/>
            </li>
            </a>
            <a href="/notifications">
            <li>
                <div class="title">
                    <img class="icon" src={bell} alt="profileIcon"/>
                    <p class="labels">Notifications</p>
                </div> 
                <img class="arrow" src={rightArrow} alt="arrow"/>
            </li>
            </a>
            <a href="/creditcard">
            <li>
                <div class="title">
                    <img class="icon" src={creditCard} alt="profileIcon"/>
                    <p class="labels">Manage Credit Cards</p>
                </div> 
                <img class="arrow" src={rightArrow} alt="arrow"/>
            </li>
            </a>
            <li>
                <div class="title">
                    <img class="icon" src={subscription} alt="profileIcon"/>
                    <p class="labels">Manage Subscriptions</p>
                </div> 
                <img class="arrow" src={rightArrow} alt="arrow"/>
            </li>
        </ul>
    </div>