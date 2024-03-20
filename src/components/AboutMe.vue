<template>
  <section id="aboutme">
    <img class="logo" src="../assets/img/logo2.png" alt="mon logo une abeille robot" />
    <div>
      <h1>Cécile Pilorger</h1>
      <img class="portrait" src="../assets/img/ma photo.png" alt="photo de cecile pilorger" />
      
    </div>
    <div class="photo">
        <h2>Des technologies à votre service</h2>
      
      <p>
        Tout est dans le nom ! marvinEssentiel propose une gamme complète
        de solutions sur mesure pour la conception graphique et le développement
        de sites web, adaptées à vos exigences et à votre budget.
      </p>
    </div>
  </section>
</template>
<style scoped>
section {
    
  width: 75%;
  margin: 5rem auto;
  background-color: #34485c;
  box-shadow: 19px 19px 15px 3px rgba(1, 4, 65, 0.3);
}
div{
    
    display: flex;
    flex-direction: column;
  align-items: center;
  justify-content: center;
}
.photo{
    margin-top: 3%;
  margin-right: 30px;
  padding-left: 80px;
  padding-right: 60px;
    display: flex;
    
    text-align: center;
}
.logo{
    margin-left: 80%;
    opacity: 0.6;
  width: 150px;
  height: 140px;
  filter: drop-shadow(40px 5px 10px rgba(0, 0, 0, 0.25));
}
p{
    color: white;
    font-family: "AbeeZee";
    
    margin-bottom: 8%;

}

.portrait{
    width: 150px;
    height: 150px;
    border-radius: 250px;
   
}
@media screen and (max-width: 600px){
  .logo{
    margin-left: 75%;
    opacity: 0.6;
  width: 80px;
  height: 75px;
  filter: drop-shadow(40px 5px 10px rgba(0, 0, 0, 0.25));
} 

}

  



</style>