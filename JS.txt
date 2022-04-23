// movement animation to happen
const card = document.querySelector('.card');
const container = document.querySelector('.container');
// item
const title= document.querySelector('.title');
const phone=document.querySelector('.phone img');
const purchase=document.querySelector('.purchase button');
const description=document.querySelector('.info h3');
// moving animation event
container.addEventListener('mousemove', (e)=>{
       let xAXIS = (window.innerWidth / 2 - e.pageX) /15;
       let yAXIS = (window.innerHeight / 2 - e.pageY)/15;
       
       card.style.transform = `rotateY(${xAXIS}deg) rotateX(${yAXIS}deg)`
});
// animate in 
container.addEventListener("mouseenter" , e=>{
       card.style.transform ="none";
       // popout
     title.style.transform = "translateZ(150px)";
     phone.style.transform = "translateZ(200px) rotateZ(-6deg)";
    description.style.transform ="translateZ(120px)"
    
     
});

// animate out
container.addEventListener("mouseleave" , e =>{
       card.style.transform="all 0.5sec ease"
       card.style.transform=`rotateY(0deg) rotateX(0deg)`;
       // popback
       title.style.transform = "translateZ(0px)";
       phone.style.transform = "translateZ(0px) rotateZ(0deg)";
       description.style.transform ="translateZ(0px)"
});