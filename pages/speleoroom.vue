<template>
    <div>
        <div style="background-image: url('/speleo/speleoMain.png'); background-size: cover;">
            <div :class="`Roboto_Regular mt-2 pt-10 ${isMobile ? 'mt-10': ''}`" 
            style="color:#C9CB67; font-size:4vw; text-align:center; line-height: 4vw;">
                Строительство спелеокомнат под ключ</div>
            <div class="Roboto_Medium mt-2" 
            :style="`color: white;text-align:center; ${isMobile ? 'font-size:12px; line-height:14px': 'font-size:1.5vw; line-height:1.8vw'} `">
                Построим вашу идеальную спелеоклиматическую камеру под ключ, качественно и в срок!</div>
            <div :class="`d-flex text-center mx-auto ${isMobile ? 'flex-column':'flex-row'} `" 
            :style="`color:white; ${isMobile ? 'width:250px;margin-top:40px;':'width:90vw;margin-top:120px;'}`">
                <div class="d-flex flex-column" :style="` ${isMobile ? 'width:100%;' : 'width:35vw;'}`">
                    <v-img class="mx-auto mb-5" width="65px" max-height="55px" src="/speleo/img1.png" />
                    <div :style="`${isMobile ? 'font-size:15px' : 'font-size:25px'}`">Разработка индивидуального дизайн-проекта</div>
                </div>
                <div :class="`d-flex flex-column ${isMobile ? 'mt-5 mb-5' : 'mr-12 ml-12'}`" :style="` ${isMobile ? 'width:100%;' : 'width:40vw;'}`">
                    <v-img class="mx-auto mb-5" width="55px" max-height="55px" src="/speleo/img2.png" />
                    <div :style="`${isMobile ? 'font-size:15px' : 'font-size:25px'}`">Создаем вентиляцию и микроклимат настоящей соляной пещеры</div>
                </div>
                <div class="d-flex flex-column" :style="` ${isMobile ? 'width:100%;' : 'width:35vw;'}`">
                    <v-img class="mx-auto mb-5" width="55px" max-height="55px" src="/speleo/img3.png" />
                    <div :style="`${isMobile ? 'font-size:15px' : 'font-size:25px'}`">Делаем  дополнительные элементы по требованию заказчика</div>
                </div>
            </div>
            <!--Диалог Узнать цену-->
            <div class="d-flex justify-center" color="transparent">
            <v-dialog v-model="dialog" width="400px" persistent content-class='asd'>
                <template v-slot:activator="{ on, attrs }">
                    <button v-bind="attrs" v-on="on" :class="`Roboto_Regular ${isMobile ? 'color_btn1_mobile':'color_btn1'}`" 
                    style="margin-top:180px; margin-bottom:100px;">
                    Узнать цену</button>
                </template>
                <div ref="form" class="align-center" width="300px" elevation="0" style="background: #C1D9C4; border-radius: 0px 40px;">
                    <div class="d-flex justify-end"><button class="pr-5 pt-2" @click="dialog = false"><v-icon>mdi-close</v-icon>
                    </button></div>
                    <v-row justify="center" class="d-flex mx-auto pb-0">
                        <v-card-title class="Roboto_Medium" style="font-size:25px; color:black; padding:0px">
                    Рассчитать смету</v-card-title></v-row>
                    <v-card-text class="Roboto_Regular d-flex justify-center" style="font-size:11px;">
                        Сделаем в течение дня расчет под ваш объем помещения.</v-card-text>
                    <v-col cols="8" justify="center" class="mx-auto" style="height:350px; margin-top:-20px">
                    <form>
                        <v-text-field :rules="nameRules" label="Имя" required color="green" outlined 
                        style="border-radius:0px 20px;"/>
                        <v-text-field :rules="emailRules" label="E-mail" required color="green" outlined style="border-radius:0px 20px;"/>
                        <v-text-field type="number" color="green" maxlength="9" :rules="numberRules" prefix="+375 " required outlined
                        style="border-radius:0px 20px;"/>
                        <v-text-field label="Сообщение" required color="green" outlined style="border-radius:0px 20px;"/>
                    </form>
                    </v-col>
                    <div class="d-flex justify-center pb-5"><button :class="`${isMobile ? 'color_btn1_mobile':'color_btn1'}`">
                        Отправить заявку</button></div>
                </div>
                </v-dialog>
            </div>
        </div>
        <div style="background-image: url('/speleo/waterSpeleo1.png'); background-size: cover;">
            <div :class="`${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Строим спелеоклиматические камеры для:</div>
            <div class="flex-row justify-center grid mb-16">
                <div class="block_salt">
                    <div class="Roboto_Medium mt-2 mb-2" style="font-size:20px">Санатория</div>
                    <v-img class="mx-auto mb-5 mt-5" height="180px" width="180px" src="/speleo/speleo1.png"/>
                </div>
                <div class="block_salt">
                    <div class="Roboto_Medium mt-2 mb-2" style="font-size:20px;line-height:20px;">Медицинских<br>учреждений</div>
                    <v-img class="mx-auto mb-5" height="180px" width="180px" src="/speleo/speleo2.png"/>
                </div>
                <div class="block_salt">
                    <div class="Roboto_Medium mt-2 mb-2" style="font-size:20px">Сауны</div>
                    <v-img class="mx-auto mb-5 mt-5" height="180px" width="180px" src="/speleo/speleo3.png"/>
                </div>
            </div>
            <div class="Roboto_Regular mx-auto pb-8" style="width:80vw; font-size:20px; text-align:center">
                <b>Спелеоклиматическая камера</b> - это специально оборудованное помещение, 
                стены, потолок и пол которого покрыты соляными брикетами. Подобная конструкция создает 
                определенную благоприятную для организма человека влажность, температуру и давление. 
                А ионный состав соляной комнаты оказывает положительное воздействие на работоспособность всего организма.
            </div>
        </div>
        <div style="background-image: url('/speleo/waterSpeleo2.png'); background-size:cover;">
            <div :class="`${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Устройства и технические характеристики на <br>
            “Спелеоклиматическую лечебницу”<br>
            <span style="color:rgba(0, 120, 15, 1);">ООО “ГринПром”</span></div>
            <div class="mx-auto pb-16 Roboto_Regular" style="width:80vw; text-align:center;font-size:20px">
                <b>“Спелеоклиматическая лечебница”</b> 
                монтируется в существующем помещении санатория или в помещениях, 
                соответствующих требованиях гигиенического норматива “Гигиенические и санитарно-микробиологические 
                показатели безопасности воздушной среды помещений организаций, занимающихся оказанием медицинской помощи. 
                Показатели безопасности наземных гало- и спелеоклиматических камер”. Состоит из спелеоклиматической камеры, 
                комнаты для подготовки пациентов и поста медсестры.<br><br>
                <b>“Спелеоклиматическая камера”</b> обеспечивает санаторно-курортное лечение, оздоровление и реабилитацию пациентов
                в условиях микроклимата, максимально приближенного к микроклимату естественных и искусственных пещер 
                (рудников, шахтах и т.д.).<br><br>
                <b>“Спелеокамера”</b> — помещение, стены и пол которого облицованы экологически чистыми брикетами (кирпичами) 
                из природных калийных руд Старобинского месторождения. Для обеспечения дополнительного контакта воздуха с 
                соляными рудами предусмотрена соляная горка с подающим воздуховодом.<br><br>
                <b>“Воздушная среда”</b> спелеокамеры воспроизводит практически все микроклиматические особенности подземной 
                спелеолечебницы на калийном руднике. Спелеоклиматическая камера обустраивается воздухообменным оборудованием
                (кондиционером канального типа и вытяжным вентилятором), обеспечивающим показатели по воздушной среде. 
                В помещении спелеокамеры монтируется бактерицидная лампа, электроосвещение, связь, подсветка и музыкальные
                колонки. Магнитофон устанавливается на посту медсестры.
                </div>
        </div>
        <div style="background-image: url('/speleo/Speleo4.png'); background-size:cover;">
            <div class="Roboto_Regular pt-10 mx-auto" style="color:#C9CB67; font-size:30px; text-align:center; line-height:30px;width:80vw;">
                Мы выполним вашу спелеоклиматическую камеру под ключ,качественно и в срок!</div>
            <div class="Roboto_Medium mt-5 mb-5 mx-auto" style="color: white; font-size:16px; text-align:center; line-height:18px;width:50vw;">
                Разработаем для вас интересное дизайнерское решение с учётом эргономики и микроклимата.</div>
            <div>
                <p class="Roboto_Regular pt-10" style="color:#C9CB67; font-size:30px; text-align:center;line-height:30px">
                    В проекте будут учтены:</p>
                    <div class="d-flex justify-center Roboto_Regular mt-6">
                        <ul style="color:white;">
                            <li>система вентиляции и микроклимата</li>
                            <li>электроснабжение</li>
                            <li>мультимедиа</li>
                            <li>освещение</li>
                            <li>комната для медперсонала</li>
                        </ul>
                    </div>
                <!--Диалог Заказать рассчет-->
                <div class="d-flex justify-center" color="transparent">
                <v-dialog v-model="dialog1" width="400px" persistent content-class='asd'>
                    <template v-slot:activator="{ on, attrs }">
                        <button v-bind="attrs" v-on="on" :class="`Roboto_Regular ${isMobile ? 'color_btn1_mobile':'color_btn1'}`" 
                        style="margin-top:100px; margin-bottom:100px;">
                        Узнать цену</button>
                    </template>
                    <div ref="form" class="align-center" width="300px" elevation="0" style="background: #C1D9C4; border-radius: 0px 40px;">
                        <div class="d-flex justify-end"><button class="pr-5 pt-2" @click="dialog1 = false"><v-icon>mdi-close</v-icon>
                        </button></div>
                        <v-row justify="center" class="d-flex mx-auto pb-0">
                            <v-card-title class="Roboto_Medium" style="font-size:25px; color:black; padding:0px">
                        Рассчитать смету</v-card-title></v-row>
                        <v-card-text class="Roboto_Regular d-flex justify-center" style="font-size:11px;">
                            Сделаем в течение дня расчет под ваш объем помещения.</v-card-text>
                        <v-col cols="8" justify="center" class="mx-auto" style="height:350px; margin-top:-20px">
                        <form>
                        <v-text-field :rules="nameRules" label="Имя" required color="green" outlined 
                        style="border-radius:0px 20px;"/>
                        <v-text-field :rules="emailRules" label="E-mail" required color="green" outlined style="border-radius:0px 20px;"/>
                        <v-text-field type="number" color="green" maxlength="9" :rules="numberRules" prefix="+375 " required outlined
                        style="border-radius:0px 20px;"/>
                        <v-text-field label="Сообщение" required color="green" outlined style="border-radius:0px 20px;"/>
                    </form>
                    </v-col>
                    <div class="d-flex justify-center pb-5"><button :class="`${isMobile ? 'color_btn1_mobile':'color_btn1'}`">
                        Отправить заявку</button></div>
                </div>
                </v-dialog>
            </div>
            </div>
        </div>
        <v-img src="/speleo/waterSpeleo333.png" style="background-size:cover;">
            <div :class="`pb-10 ${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Достоинства спелеоклиматической камеры<br>
                <span style="color:rgba(0, 120, 15, 1);">ООО “ГринПром”</span></div>
            <div class="Roboto_Regular mx-auto pb-16" style="width:80vw; text-align:center;font-size:20px">
                Достоинством такого лечебно-профилактического помещения является то, что здесь 
                <b>наблюдается полное отсутствие всевозможных аллергенов и патогенных бактерий</b>. С давних пор спелеокамеры 
                эффективно используются в лечебных, а также в профилактических целях. Доказано, что заболевший человек 
                после посещения спелеокамеры <b>выздоравливает гораздо быстрее</b>. При этом процесс выздоровления возможен без 
                использования медикаментозных методов терапии. Основная терапевтическая польза спелеокамеры заключена в том, 
                что человек находится под воздействием формирующейся воздушной лечебной среды. В результате посещения спелеокамеры
                происходит <b>стимуляция метаболизма</b> (улучшения работы обменных процессов) благодаря которой из организма происходит
                высвобождение токсических компонентов, пагубно влияющих на здоровье человека. Многие специалисты уверяют, 
                что процедуру посещения спелеокамеры можно сравнить с полноценным отдыхом на причерноморском курорте. Посещение
                спелеокамеры оказывает <b>восстанавливающий эффект: снимает хроническую усталость, стресс после изнурительной болезни 
                или при расстройствах нервной системы</b>.</div>
        </v-img>
        <div>
            <div :class="`${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Спелеокомната “Классик”<br>
            <span style="color:rgba(0, 120, 15, 1);">ООО “ГринПром”</span></div>
            <div class="Roboto_Medium text-center mb-8" style="font-size:25px">Что входит в стоимость строительства соляной комнаты?</div>
            <v-img class="mx-auto mb-10" width="750px" src="/speleo/speleo_klassik.png"/>
            <ul class="Roboto_Medium d-flex justify-center mb-10">
                <ol>
                    <li>Дизайн — проект.</li>
                    <li>Монтаж соляных блоков(пол и стены).</li>
                    <li>Элементы дизайна с подсветкой или без.</li>
                    <li>Системы вентиляции и микроклимата.</li>
                    <li>Аудио система.</li>
                    <li>Освещение.</li>
                    <li>Электромонтаж оборудования.</li>
                    <li>Натяжной потолок.</li>
                    <li>Пусконаладочные работы.</li>
                    <li>Дополнительные элементы по требованию заказчика.</li>
                </ol>
            </ul>
            <div class="Roboto_Medium mx-auto text-center mb-10" style="background:#C1D9C4; border-radius:0px 30px; width:350px;">
                Сроки выполнения — от 30 до 60 дней.</div>
        </div>
        <div :class="`${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Наши работы и материалы 
        <span style="color:rgba(0, 120, 15, 1);">ООО “ГринПром”</span></div>
        <!--картинки листать-->
        <div class="mx-auto mb-16" style="background:rgba(132, 180, 137, 1); width:80%; border-radius: 0px 40px;">
            <v-carousel :show-arrows="false" v-model="item" :height="`${isMobile ? '42vw': '35vw'}`"
            style="border-radius: 0px 40px;">
                    <v-carousel-item v-for="(slide, i) in slides" :value="i" :key="i" >
                        <div class="text-center Roboto_Medium" style="position:relative; margin-top:2vw ; color:white; font-size:2vw">
                            {{slide.name}}
                        </div>
                        <v-img style="margin:1vw" :src="slide.src1" />
                    </v-carousel-item>
            </v-carousel>
        </div>
        <div style="background-image: url('/speleo/water_video.png'); background-size: cover; height: 50vw;">
            <div class="d-flex justify-center" style="height:100%">
                <div class="my-auto pt-10">
                    <video ref="videoPlayer" :width="`${isMobile ? '375px': '800px'}`" loop muted controls>
                        <source src="/speleo/mp4/video.mp4" type="video/mp4">
                    </video>
                </div>
            </div>
        </div>
        <div style="background:#C1D9C4;">
            <div :class="`${isMobile ? 'zagalovok_mobile': 'zagalovok'}`">Остались вопросы?</div>
            <div :class="`Roboto_Medium mt-2 ${isMobile ? 'mt-10': ''}`" 
            style=" font-size:16px; text-align:center; line-height: 18px;">
                Оставьте заявку на бесплатный замер.<br>Созвонимся и договоримся о времени выезда.</div>
            <div>
                <v-col :cols="`${isMobile ? '8': '4'}`" justify="center" class="mx-auto" style="height:; margin-top: 4vw;">
                    <form>
                        <v-text-field :rules="nameRules" label="Имя" required color="green" outlined 
                        style="border-radius:0px 20px;"/>
                        <v-text-field type="number" color="green" maxlength="9" :rules="numberRules" prefix="+375 " required outlined
                        style="border-radius:0px 20px;"/>
                    </form>
                </v-col>
                <div class="d-flex justify-center">
                    <button :class="`Roboto_Regular ${isMobile ? 'color_btn1_mobile':'color_btn1'}`" 
                        style="margin-top:20px; margin-bottom:60px;">
                        Отправить заявку</button>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.v-carousel__controls {
    height: 35px;
}
.v-carousel__controls__item{
      margin-top: 0;
}

input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
}
.my-text-style{
    color: red;
  }

.asd{
  border-radius: 0px;
  box-shadow: none;
}
</style>

<script>
export default {
    data(){
        return{
            dialog: false,
            dialog1: false,
            item: 0,
            nameRules: [
                v => !!v || 'Укажите имя',
                v => (v && v.length <= 10) || 'Имя должно быть не больше 10 символов',
            ],
            numberRules: [
                v => !!v || 'Укажите номер вашего телефона',
                v => (v && v.length <= 9) || 'Номер телефона должно быть не больше 9 символов',
            ],
            emailRules: [
                v => !!v || 'Укажите вашу почту',
                v => /.+@.+/.test(v) || 'Электронная почта должна быть действующей',
            ],
            slides:{
                slide1: {
                    src1: '/speleo/slide1.png',
                    name: 'Детский санаторий ОАО “Белагроздравница” Налибокская пуща'
                    },
                slide2: {
                    src1: '/speleo/slide2.png',
                    name: 'Детский санаторий ОАО “Белагроздравница” Сосновый бор'
                    },
                slide3:{
                    src1: '/speleo/slide4.png',
                    name: 'Санаторий ОАО«Белагроздравница» Поречье'
                    },
                slide4:{
                    src1: '/speleo/slide5.png',
                    name: 'Санаторий ОАО«Белагроздравница» Березина'
                    },
                },
        }
    },
    computed:{
    isMobile:{
      get(){
        return this.$store.getters.isMobile;
      }
    },
  },
}

</script>
