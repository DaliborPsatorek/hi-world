<template>
    <main>
        <h1>Zoznam ľudí</h1>
        <section class="list">
            <section
                v-for="person of persons"
                v-bind:key="person"
                v-bind:class="{
                    'card-container': true,
                    card: true,
                    adult: personAge(person.birthday) >= 18,
                }"
            >
                <PersonalCard v-bind:person="person"></PersonalCard>
            </section>
        </section>
        <div class="button" @click="deleteAll()">DELETE ALL</div>
    </main>
</template>

<script setup>
const date = new Date();
let year = date.getFullYear();
let persons = ref([
    {
        fname: "Magdalena",
        lname: "Mikulova",
        birthday: 2000,
    },
    {
        fname: "Mirka",
        lname: "Makovicova",
        birthday: 1992,
    },
    {
        fname: "Hugo",
        lname: "Hugovic",
        birthday: 2007,
    },
    {
        fname: "Miki",
        lname: "Hric",
        birthday: 2003,
    },
    {
        fname: "Andrea",
        lname: "Veresova",
        birthday: 1982,
    },
    {
        fname: "Nora",
        lname: "Mojsejova",
        birthday: 2009,
    },
]);
let personAge = (birthday) => {
    return ref(year - birthday), year - birthday;
};

let deleteAll = () => {
    persons.value = [];
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;500;600;700&display=swap");
body {
    background-color: #9fb2bc70;
    font-size: 10px;
    font-family: "Oswald", sans-serif;
    padding: 1rem;
}
main {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
}
.list {
    display: flex;
    gap: 20px;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: stretch;
    font-size: 1.2rem;
}
.card-container {
    flex-grow: 1;
}
.button {
    text-align: center;
    font-size: xx-large;
    height: 3rem;
    width: 20rem;
    color: white;
    background-color: red;
}
</style>
