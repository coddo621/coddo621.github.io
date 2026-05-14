<style>
    .nav {
        position: fixed;
        top: 0;
        left: 50%;
        transform: translateX(-50%);
        z-index: 50;

        display: flex;
        flex-direction: row;
        align-items: center;
        white-space: nowrap;
        width: max-content;

        margin-top: 1rem;   
        padding: 0.5rem 1rem;
        
        background-color: rgba(255, 255, 255, 0.3);
        backdrop-filter: blur(12px);
        -webkit-backdrop-filter: blur(12px);
        
        border: 2px solid #ffa552; 
        border-radius: 0.75rem;
    }

    a {
        font-size: 3rem; 
        text-decoration: none;
        padding: 0.5rem 1rem;
        color: #000000;
        transition: transform 0.1s ease;
    }

    a:hover {
        transform: scale(1.1);
    }
</style>

<div class="nav">
    <a href="#hero">/</a>
    <a href="#projects">Projects</a>
    <a href="#gallery">Gallery</a>
</div>