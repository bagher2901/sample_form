<template>
    <div>
        <div class="container">
            <div class="row mt-2 mb-3">
                <div class="col-lg-8 offset-lg-2 col-md-10 offset-md-1  col-sm-12">
                    <div class="row">
                        <form class="row g-2">

                            <div class="col-md-6">
                                <label class="form-label">firstname</label>
                                <input type="text" class="form-control " v-model="first_name" placeholder="Frodo ">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label">lastname</label>
                                <input type="text" class="form-control" v-model="last_name" placeholder="Baggins">
                            </div>

                            <div class="col-md-6">
                                <label class="form-label">Email</label>
                                <input type="email" class="form-control" v-model="email"
                                       placeholder="Frodo@example.com">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label">Password</label>
                                <input type="password" class="form-control" v-model="password" placeholder="********">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label">Personal Code</label>
                                <input type="text" class="form-control" v-model="personal_code" placeholder="FB452111">
                            </div>
                            <hr>
                            <div class="col-12">

                                <label class="form-label">Address</label>
                                <input type="text" class="form-control" v-model="address.main_st"
                                       placeholder="1234 Main St">
                            </div>
                            <div class="col-12">
                                <label class="form-label">Address 2</label>
                                <input type="text" class="form-control" v-model="address.apartment"
                                       placeholder="Apartment, studio, or floor">
                            </div>
                            <div class="col-md-6">
                                <label class="form-label">City</label>
                                <input type="text" class="form-control" v-model="address.city" placeholder="Shire">
                            </div>
                            <hr>
                            <div class="col-md-6">
                                <label class="form-label">University,College,Academy </label>
                                <input type="text" class="form-control" v-model="university.un_name"
                                       placeholder="Oxford">
                            </div>
                            <div class="col-md-4">
                                <label class="form-label">Level of Education</label>
                                <select v-model="university.level" class="form-select">
                                    <option>Illiterate</option>
                                    <option>Diploma</option>
                                    <option>A.D.</option>
                                    <option>B.S.</option>
                                    <option>M.S.</option>
                                    <option>Ph.D.</option>
                                </select>
                            </div>


                            <div class="col-12">
                                <label class="form-label">Marital Status : </label>
                                <div class="form-check form-check-inline">

                                    <input class="form-check-input" type="radio" value="married" v-model="marital_state"
                                           name="flexRadioDefault"
                                           id="flexRadioDefault1">
                                    <label class="form-check-label" for="flexRadioDefault1">
                                        Married
                                    </label>
                                </div>
                                <div class="form-check form-check-inline">
                                    <input class="form-check-input" type="radio" value="single" v-model="marital_state"
                                           name="flexRadioDefault"
                                           id="flexRadioDefault2" checked>
                                    <label class="form-check-label" for="flexRadioDefault2">
                                        Single
                                    </label>
                                </div>


                            </div>


                            <div class="col-12 mb-3">
                                <button type="submit" @click="submited" class="btn btn-primary">Sign in</button>
                            </div>
                        </form>
                    </div>
                </div>

            </div>
        </div>
    </div>
    </div>
</template>

<script>


    export default {
        name: 'App',
        data() {
            return {
                first_name: '',
                last_name: '',
                email: '',
                password: '',
                personal_code: '',
                address: {
                    city: '',
                    main_st: '',
                    apartment: ''
                },
                university: {
                    un_name: '',
                    level: ''
                },
                marital_state: ''
            }
        },
        components: {},
        methods: {
            submited() {
                console.log(this.first_name)
                //console.log(this.marital_state)
                console.log(this.university.level)
            }
        }
    }
</script>

<style>
    .container {
        background-color: #0ef0bf2d;
        border-radius: 8px;
        min-height: 700px;
        min-width: 550px;
    }

    /* width */
    ::-webkit-scrollbar {
        width: 6px;
    }

    /* Track */
    ::-webkit-scrollbar-track {
        background: #0ef0bf2d;

    }

    /* Handle */
    ::-webkit-scrollbar-thumb {
        background: #0d6efd;
        border-radius: 50px;
    }

    /* Handle on hover */
    ::-webkit-scrollbar-thumb:hover {
        background: #0761e7;
    }
</style>
