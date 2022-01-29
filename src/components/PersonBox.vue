<template>
    <section class="person-box info-container">
          <h2  class="person-box-header">{{person.first_name}} {{person.last_name}}</h2>
          <section class="person-image"></section>
            <section class="person-info">
              Person
            </section>
        </section>
</template>

<script>

export default({
    name: 'person-box',
    props: ['person']
})
</script>
