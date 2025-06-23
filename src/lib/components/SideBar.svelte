<script>

</script>

<div id="side_container">
    <div id="content_tittle">
        <h1 id="tittle">SchoolManager</h1>
    </div>

    <div id="itens_sidebar">
        <a href="/">DashBoard</a>
        <a href="/Courses">Courses</a>
        <a href="/Subjects">Subjects</a>
        <a href="/Students">Students</a>
        <a href="/Enrollments">Enrollments</a>
        <a href="/Settings">Settings</a>
    </div>
</div>

<style>
    #content_tittle{
        text-align: center;
    }
    #side_container{
        font-family: "Roboto";
        width: 20dvw;
        height: 100dvh;
        display: flex;    
        flex-direction: column;
        padding: 10px;
        border: 1px solid #9ca3af;
    }
    #itens_sidebar{
        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 15px;
    }
    #itens_sidebar a{
        color: #374151;
        font-size: 1rem; 
    }
</style>
