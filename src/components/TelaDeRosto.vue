<template id = 'Fundo'>
    <div id='Container'>
        <h1 id = 'Titulo'>Barbearia X</h1>
        <h2 id='Subtitulo'>O melhor sistema de barbearias do Brasil</h2>
        <h3 id='SubtituloServicos'>Todos os serviços voltados para a beleza masculina</h3>
        <h3 id='SubtituloLocalizacao'>Goiânia Goiás</h3>
        <img src="../assets/BarberPole.svg" alt="BarberPole" id='BarberPole'>
        <img src="../assets/hairstyle.svg" alt="Barber" id='Barber'>
        <button type="">-></button>
    
    </div>
    
    
</template>

<script>
    export default{

    }
</script>

<style scoped>

    #container {
        background-color: blue;
    }

    #fundo{
        background-color: blue;
    }

    #Titulo  {

        position: absolute;
        width: 275px;
        height: 68px;
        left: 237px;
        top: 125px;

        font-family: Nunito;
        font-style: normal;
        font-weight: 800;
        font-size: 50px;
        line-height: 68px;

        color: #FCFCFC;

         /*border: 1px solid #000000;*/

        text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

    }

    #Subtitulo {

        position: absolute;
        width: 398px;
        height: 283px;
        left: 93px;
        top: 270px;

        font-family: Nunito;
        font-style: normal;
        font-weight: 800;
        font-size: 50px;
        line-height: 68px;

        color: #FCFCFC;

        /*border: 1px solid #000000;*/
        backdrop-filter: blur(4px);
    }

    #BarberPole {

        position: absolute;
        width: 98px;
        height: 230px;

    }

    #SubtituloServicos {

        position: absolute;
        width: 526px;
        height: 66px;
        left: 80px;
        top: 540px;

        font-family: Nunito;
        font-style: normal;
        font-weight: 800;
        font-size: 20px;
        line-height: 27px;

        color: #FCFCFC;

       /* border: 1px solid #000000;*/
        backdrop-filter: blur(4px);

    }

    #Barber {

        position: absolute;
        width: 500px;
        height: 500px;
        left: 580px;
        /*top: 1px;*/

    }

    #SubtituloLocalizacao {

        position: absolute;
        width: 83px;
        height: 68px;
        left: 1197px;
        top: 123px;

        font-family: Nunito;
        font-style: normal;
        font-weight: 800;
        font-size: 24px;
        line-height: 34px;
        color: #FFFFFF;

    }

    #Seta {
        position: absolute;
        width: 80px;
        height: 80px;
        left: 1200px;
        top: 620px; 

        background: #F2F2F2;
        border-radius: 30px
    }

</style>

