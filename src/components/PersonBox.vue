<template>
    <article class="box person-box info-container">
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
                </table>
                </section>
                <section class="person-info-first-table">
                    <table class="person-info-table">
                  <tr>
                      <td class="person-info-data-name">Adress</td>
                      <td class="person-info-data-personal">{{adress.city}}, {{adress.street_name}}, {{adress.street_address}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">ZIP Code</td>
                    <td class="person-info-data-personal">{{adress.zip_code}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">State</td>
                    <td class="person-info-data-personal">{{adress.state}}</td>
                  </tr>
                  <tr>
                    <td class="person-info-data-name">Country</td>
                    <td class="person-info-data-personal">{{adress.country}}</td>
                  </tr>
                  <tr colspan="2">
                    <td class="person-info-data-name">Job</td>
                    <td>{{job.title}}</td>
                  </tr>
                </table>
                </section>
            </section>
            <section class="social-networks">
                <button v-on:click="showModal = true" class="person-modal-open-button">Learn More</button>
            </section>
        </article>


        <section class="modal-window" v-if="showModal">
            <section class="modal-wrapper">
                <section class="modal-container">
                    <table>
                        <tr>
                            <td class="person-info-data-name">Gender</td>
                            <td class="person-info-data-personal">{{person.gender}}</td>
                        </tr>
                        <tr>
                            <td class="person-info-data-name">SI Number</td>
                            <td class="person-info-data-personal">{{person.social_insurance_number}}</td>
                        </tr>
                </table>
                <hr>
                        <table>
                            <tr>
                                <td class="person-info-data-name">Subscription Plan</td>
                                <td class="person-info-data-personal">{{subscription.plan}}</td>
                            </tr>
                            <tr>
                                <td class="person-info-data-name">Subscription Status</td>
                                <td class="person-info-data-personal">{{subscription.status}}</td>
                            </tr>
                            <tr>
                                <td class="person-info-data-name">Payment Method</td>
                                <td class="person-info-data-personal">{{subscription.payment_method}}</td>
                            </tr>
                            <tr>
                                <td class="person-info-data-name">Term</td>
                                <td class="person-info-data-personal">{{subscription.term}}</td>
                            </tr>
                        </table>
                    <button v-on:click="showModal = false" class="modal-button">Close</button>
                </section>
            </section>
        </section>
</template>

<script>



export default({
    name: 'person-box',
    props: ['person', 'job', 'adress', 'subscription'],
    data() {
        return {
            showModal: false
        }
        
    }
    
    
})
</script>
