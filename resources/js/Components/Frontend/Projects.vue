<script setup>
import Project from '@/Components/Frontend/Project.vue'
    defineProps({
        skills:{},
        projects: {}
    })
    
</script>

<template>
    <div class="container mx-auto">
        <nav class="mb-12 border-b-2 border-light-tail-100 dark:text-dark-navy-100">\
            <ul class="flex flex-col lg:flex-row justify-evenly items-center">
                <li class="cursor-pointer capitalize m-4">
                    <button class="flex text-center px-4 py-2 first-letter: hover:bg-accent dark:text-white rounded-md">
                        All
                    </button>
                </li>
                <li class="cursor-pointer capitalize m-4" v-for="projectSkill in skills.data" :key="projectSkill.id">
                    <button class="flex text-center px-4 py-2 first-letter: hover:bg-accent dark:text-white rounded-md">
                        {{projectSkill.name}}
                    </button>
                </li>
            </ul>        
        </nav>
        <section class="grid gap-y-12 lg:grid-cols-3 lg:gap-8">
            <div v-if="projects">
                <Project v-for="project in projects.data" :key="project.id" :project="project" />
            </div>
        </section>   
    </div>
</template>