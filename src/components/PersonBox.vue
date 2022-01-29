<template>
    <section class="person-box info-container">
          <h2  class="person-box-header">{{person.first_name}} {{person.last_name}}</h2>
          <img :src=person.avatar class="person-image"/>
            <section class="person-info">
                <section class="person-info-first-table">
                    <table class="person-info-table">
                  <tr>
                      <td class="person-info-data-name">UserName</td>
                      <td>{{person.username}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">E-Mail</td>
                    <td>{{person.email}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Phone Number</td>
                    <td>{{person.phone_number}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Date Of Birth</td>
                    <td>{{person.date_of_birth}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Job</td>
                    <td>{{job.title}}</td>
                  </tr>
                </table>
                </section>
                <section class="person-info-first-table">
                    <table class="person-info-table">
                  <tr>
                      <td class="person-info-data-name">Adress</td>
                      <td class="person-info-data-personal">{{adress.city}}, {{adress.street_name}}, {{adress.street_address}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">E-Mail</td>
                    <td class="person-info-data-personal">{{person.email}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Phone Number</td>
                    <td class="person-info-data-personal">{{person.phone_number}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Date Of Birth</td>
                    <td class="person-info-data-personal">{{person.date_of_birth}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Job</td>
                    <td>{{job.title}}</td>
                  </tr>
                </table>
                </section>
            </section>
        </section>
</template>

<script>


export default({
    name: 'person-box',
    props: ['person', 'job', 'adress'],
    
})
</script>
