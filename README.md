# Firebase-Tutorial
Firebase tutorial

#### step 1 : Clone the code 

#### step 2 : setup firebse and paste the configuration code (configration code example given below **Don't COPY THIS CONFIGRATION CODE IT'S UNIQUE FOR ALL**) on html file below body tag ( </body> )
[DOCS](https://https://www.bit.ly/Firebasedoc)

    <script type="module">
    // Import the functions you need from the SDKs you need
    import { initializeApp } from "https://www.gstatic.com/firebasejs/9.12.1/firebase-app.js";
    // TODO: Add SDKs for Firebase products that you want to use
    // https://firebase.google.com/docs/web/setup#available-libraries

    // Your web app's Firebase configuration
    const firebaseConfig = {
        apiKey: "AIzaSyC_Acy3h5J5Egbj8Mc1CxAXCaS3M-hEWDs",
        authDomain: "fir-4b6c7.firebaseapp.com",
        projectId: "fir-4b6c7",
        storageBucket: "fir-4b6c7.appspot.com",
        messagingSenderId: "643012676626",
        appId: "1:643012676626:web:6cf897e4f8fc5df55e9ccb"
    };

    // Initialize Firebase
    const app = initializeApp(firebaseConfig);
    </script>
    
    
    
#### step 3 : paste the below code in the script (consider the figure 1:import packages)

    import { getFirestore, addDoc, collection, getDocs } from 'https://www.gstatic.com/firebasejs/9.12.1/firebase-firestore.js'
    
![image](https://user-images.githubusercontent.com/70875875/198297933-c2294803-3b28-4567-bfba-483602ee3a15.png)

#### step 4 : Paste the below code for initialize database (note highlighted area Figure 3:Database initilizing)

     const db = getFirestore(app);
     
![image](https://user-images.githubusercontent.com/70875875/198299526-b6e3adaf-41ab-44c6-9cfa-212669a0557b.png)
     
#### step 5 : Paste the below code to data sent (like in figure 2:data sending)

## Data send

    document.getElementById("submit-btn").onclick = async function (e) {
        e.preventDefault()
        const docRef = await addDoc(collection(db, "data"), {
            Name: document.getElementById('Name').value,
            Message: document.getElementById('Msg').value
        });
        console.log("Document written with ID: ", docRef.id);
        alert("Form submitted")
        location.reload()
    };
    
![image](https://user-images.githubusercontent.com/70875875/198335341-0208301a-2000-45b0-9854-bf76f7deecc9.png)

#### step 6 : Paste the below code as in picture (note Figure 3:Data sending)

## Data Calling

    window.onload = async function () {
        const querySnapshot = await getDocs(collection(db, "data"));
        querySnapshot.forEach((doc) => {
            const row = document.getElementById("tbody").insertRow(0);
            row.insertCell(0).innerHTML = doc.data().Name
            row.insertCell(-1).innerHTML = doc.data().Message
        });
    }

![image](https://user-images.githubusercontent.com/70875875/198315253-60427304-4025-47ba-a3e7-f40742b0f44f.png)

#### step 7 : Type somthing in website form and submit. Then refresh the website to see the change (note in video)

![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/70875875/198913787-1a1fa426-c474-4c0f-bcfa-ee75b9639ff3.gif)

<!--[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/HyiNbqLOCQ8/0.jpg)](https://www.youtube.com/watch?v=HyiNbqLOCQ8)-->

##### After you submit, the firestore database will be like this ->

![image](https://user-images.githubusercontent.com/70875875/198336447-a8311179-0bcb-4118-ac53-697d88236a50.png)


