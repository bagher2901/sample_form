<template>

    <div class="container">


        <div class="row mt-2 mb-3">
            <select class="form-select" v-model="currentlocale" v-bind:class="{'fa_box':currentlocale==='fa'}">
                <option v-for="locale in locales" :value="locale.id">{{locale.name}}</option>
            </select>
            <div class="col-lg-8 offset-lg-2 col-md-10 offset-md-1  col-sm-12"
                 v-bind:class="{'fa_box':currentlocale==='fa'}">
                <div class="row">
                    <form class="row g-2">

                        <div class="col-md-6">
                            <label class="form-label">{{label_box.first_name[currentlocale]}}</label>
                            <input type="text" class="form-control " v-model="information.first_name"
                                   placeholder="Frodo ">
                        </div>
                        <div class="col-md-6">
                            <label class="form-label">{{label_box.last_name[currentlocale]}}</label>
                            <input type="text" class="form-control" v-model="information.last_name"
                                   placeholder="Baggins">
                        </div>

                        <div class="col-md-6">
                            <label class="form-label">{{label_box.email[currentlocale]}}</label>
                            <input type="email" class="form-control" v-model="information.email"
                                   placeholder="Frodo@example.com">
                        </div>
                        <div class="col-md-6">
                            <label class="form-label">{{label_box.password[currentlocale]}}</label>
                            <input type="password" class="form-control" v-model="information.password"
                                   placeholder="********">
                        </div>
                        <div class="col-md-6">
                            <label class="form-label">{{label_box.personal_code[currentlocale]}}</label>
                            <input type="text" class="form-control" v-model="information.personal_code"
                                   placeholder="FB452111">
                        </div>
                        <hr>
                        <div class="col-12">
                            <label class="form-label">{{label_box.main_address[currentlocale]}}</label>
                            <input type="text" class="form-control" v-model="information.address.main_st"
                                   placeholder="1234 Main St">
                        </div>
                        <div class="col-12">
                            <label class="form-label">{{label_box.sub_address[currentlocale]}}</label>
                            <input type="text" class="form-control" v-model="information.address.apartment"
                                   placeholder="Apartment, studio, or floor">
                        </div>
                        <div class="col-md-6">
                            <label class="form-label">{{label_box.city[currentlocale]}}</label>
                            <input type="text" class="form-control" v-model="information.address.city"
                                   placeholder="Shire">
                        </div>
                        <hr>
                        <div class="col-md-6">
                            <label class="form-label">{{label_box.uni[currentlocale]}} </label>
                            <input type="text" class="form-control" v-model="information.university.un_name"
                                   placeholder="Oxford">
                        </div>
                        <div class="col-md-4">
                            <label class="form-label">{{label_box.level[currentlocale]}}</label>
                            <select v-model="information.university.level" class="form-select">
                                <option>{{label_box.illiterate[currentlocale]}}</option>
                                <option>{{label_box.diploma[currentlocale]}}</option>
                                <option>{{label_box.ad[currentlocale]}}</option>
                                <option>{{label_box.bs[currentlocale]}}</option>
                                <option>{{label_box.ms[currentlocale]}}</option>
                                <option>{{label_box.phd[currentlocale]}}</option>
                            </select>
                        </div>


                        <div class="col-12">
                            <label class="form-label"> {{label_box.m_state[currentlocale]}} : </label>
                            <div class="form-check form-check-inline">

                                <input class="form-check-input" type="radio" value="married"
                                       v-model="information.marital_state"
                                       name="flexRadioDefault"
                                       id="flexRadioDefault1">
                                <label class="form-check-label" for="flexRadioDefault1">
                                    {{label_box.married[currentlocale]}}
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" value="single"
                                       v-model="information.marital_state"
                                       name="flexRadioDefault"
                                       id="flexRadioDefault2" checked>
                                <label class="form-check-label" for="flexRadioDefault2">
                                    {{label_box.single[currentlocale]}}
                                </label>
                            </div>


                        </div>


                        <div class="col-12 mb-3">
                            <button type="submit" @click="submited" class="btn btn-primary">
                                {{label_box.sign[currentlocale]}}
                            </button>
                        </div>
                    </form>
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
                information: {
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
                },
                currentlocale: 'en',
                locales: [{id: 'en', name: 'English'}, {id: 'fa', name: 'Persian'}],
                label_box: {
                    first_name: {
                        en: 'First Name',
                        fa: 'نام'
                    },
                    last_name: {
                        en: 'Last Name',
                        fa: 'نام خانوادگی'
                    },
                    email: {
                        en: 'Email',
                        fa: 'ایمیل'
                    },
                    password: {
                        en: 'Password',
                        fa: 'رمز'
                    },
                    personal_code: {
                        en: 'Personal Code',
                        fa: 'کد پرسنلی'
                    },
                    main_address: {
                        en: 'Address',
                        fa: 'خیابان اصلی'
                    },
                    sub_address: {
                        en: 'address 2',
                        fa: 'خیابان فرعی'
                    },
                    city: {
                        en: 'City',
                        fa: 'شهر'
                    },
                    uni: {
                        en: 'University,College,Academy',
                        fa: 'دانشگاه،آکادمی،آموزشگاه'
                    },
                    level: {
                        en: 'Level of Education',
                        fa: 'سطح تحصیلات'
                    },
                    m_state: {
                        en: 'Marital Status',
                        fa: 'وضعیت تاهل'
                    },
                    sign: {
                        en: 'Sign in',
                        fa: 'ثبت نام'
                    },
                    married: {
                        en: 'Married',
                        fa: 'متاهل'
                    },
                    single: {
                        en: 'Single',
                        fa: 'مجرد'
                    },
                    illiterate: {
                        en: 'Illiterate',
                        fa: 'بی سواد'
                    },
                    diploma: {
                        en: 'Diploma',
                        fa: 'دیپلم'
                    },
                    ad: {
                        en: 'A.D.',
                        fa: 'فوق دیپلم'
                    },
                    bs: {
                        en: 'B.S.',
                        fa: 'کارشناسی'
                    },
                    ms: {
                        en: 'M.S.',
                        fa: 'کارشاسی ارشد'
                    },
                    phd: {
                        en: 'Ph.D.',
                        fa: 'دکترا'
                    }

                },


            }
        },
        components: {},
        methods: {
            submited: function () {
                console.log(this.information)
            },

        }
    }
</script>

<style>
    .fa_box {
        direction: rtl;
        text-align: right;


    }

    .en_box {
        direction: ltr;
        text-align: left;


    }

    .container {
        background-color: #0ef0bf2d;
        border-radius: 8px;
        min-height: 700px;
        min-width: 630px;
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
