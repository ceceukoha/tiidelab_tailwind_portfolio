<template>
    <div >
        <!-- <h1>Home</h1> -->
        <div class="home-page">
            <p>Repo Manager </p>
        <!-- <h3>Get Access to your Repos <br> Anywhere <br> Anytime</h3> -->


        <RouterLink to="/repo" class="btn btn-secondary w-25 home-page-btn">Get Started</RouterLink>
        </div>
        
        
    </div>
    
</template>
<style>
.home-page{
    width: 100%;
}
.home-page h1{
    font-size: 3rem;
}
.home-page h3{
    font-size: 1.3rem;
    text-align: center;
    margin-top: 20px;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

}
.home-page p{
    margin-top: 90px;
    margin-bottom: 90px;
    font-size: 1.5rem;
    text-align: center;
    font-family: "Righteous", sans-serif;
    font-size: 70px;
    overflow: hidden;
}
.home-page-btn{
    margin-top: 90px;

    font-size: 1.2rem;
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    margin: auto;


    background-color: #2da44e;
    border: none;
    border-radius: 6px;
    padding: 12px 10px;
    color: white;


}
</style>