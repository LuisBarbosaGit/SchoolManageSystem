<script>
    import { HouseIcon, BookOpenIcon, UsersIcon, UserCheckIcon, SettingsIcon, GraduationCapIcon } from "@lucide/svelte";
</script>

<div id="side_container">
    <div id="content_tittle">
        <h1 id="tittle">Menu</h1>
    </div>

    <div id="itens_sidebar">
        <a href="/"><HouseIcon />DashBoard</a>
        <a href="/courses"> <BookOpenIcon />Courses</a>
        <a href="/subjects"><GraduationCapIcon />Subjects</a>
        <a href="/students"><UsersIcon />Students</a>
        <a href="/enrollments"><UserCheckIcon />Enrollments</a>
        <a href="/Settings"><SettingsIcon />Settings</a>
    </div>
</div>

<style>
    #content_tittle{
        display: flex;
        justify-content: center;
        font-size: 0.8rem;
        border-bottom: 1px solid #545c67;
    }
    #side_container{
        font-family: "Roboto";
        width: 15rem;
        display: flex;    
        flex-direction: column;
        border: 1px solid #adb3be;
        min-width: 10rem;
        height: 99dvh;
        background-color: white;
    }
    #itens_sidebar{
        margin-top: 10px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 20px;
        margin-left: 0.6rem;
        padding: 10px;
    }
    #itens_sidebar a{
        display: flex;
        align-items: center;
        gap: 10px;
        color: #374151;
        font-size: 1rem; 
        
    }
    #itens_sidebar a:hover{
        transform: scale(1.02);
        transition: all 0.1s ease-in;
    }
    
</style>
