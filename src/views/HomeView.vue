<template>
  <div class="q-pa-md">
    <q-toolbar class="q-ma-sm">
      <q-input
        outlined
        v-model="text"
        label="Search"
        :dense="dense"
        rounded
        class="search"
      >
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
      <q-space></q-space>
      <q-btn color="white" text-color="black" icon="fas fa-moon" />
    </q-toolbar>
    <q-toolbar>
      <h6 class="text-weight-bolder">Dashboard</h6>
      <q-space></q-space>
      <q-icon name="fas fa-calendar-minus" size="" class="q-mr-sm" />
      <div class="text-overline">Wednesday, 21.03.2022</div>
    </q-toolbar>
    <div class="row q-col-gutter-md top">
      <div class="col-3">
        <q-card class="q-mx-md" bordered>
          <div class="flex flex-center column">
            <q-circular-progress
              show-value
              font-size="12px"
              value="70"
              size="100px"
              :thickness="0.22"
              color="green-7"
              track-color="green-2"
              class="q-ma-md"
            >
              784 Patients
            </q-circular-progress>
            <div>
              <q-badge color="green-2" rounded class="q-mr-sm" />Woman 40%
            </div>
            <div class="q-mb-xl">
              <q-badge color="green-7" rounded class="q-mr-sm" />Man 60%
            </div>
          </div>
        </q-card>
      </div>
      <div class="col-3">
        <q-card class="q-mx-md q-pa-md" bordered>
          <div class="text-overline">New patients</div>
          <div class="flex flex-center row">
            <div class="text-h4 text-weight-bolder q-mr-md">54</div>
            <q-chip
              color="green-1"
              text-color="green-3"
              icon="fas fa-chevron-up"
              >51%</q-chip
            >
          </div>
        </q-card>
        <q-card class="q-mx-md q-pa-md q-mt-sm" bordered>
          <div class="text-overline">Old patients</div>
          <div class="flex flex-center row">
            <div class="text-h4 text-weight-bolder q-mr-md">32</div>
            <q-chip color="red-1" text-color="red-3" icon="fas fa-chevron-down"
              >02%</q-chip
            >
          </div>
        </q-card>
      </div>
      <div class="col-6">
        <q-card class="q-mx-md q-pa-md doctors" bordered>
          <div class="text-overline">Statistic</div>
          <div class="">
            <q-carousel
              v-model="slide"
              vertical
              transition-prev="slide-down"
              transition-next="slide-up"
              swipeable
              animated
              control-color="green-7"
              navigation-icon="radio_button_unchecked"
              navigation
              padding
              arrows
              height="160px"
              class="text-black shadow-1 rounded-borders"
            >
              <q-carousel-slide name="style" class="column no-wrap flex-center">
                <q-icon name="style" size="36px" />
                <div class="q-mt-md text-center">
                  {{ lorem }}
                </div>
              </q-carousel-slide>
              <q-carousel-slide name="tv" class="column no-wrap flex-center">
                <q-icon name="live_tv" size="36px" />
                <div class="q-mt-md text-center">
                  {{ lorem }}
                </div>
              </q-carousel-slide>
              <q-carousel-slide
                name="layers"
                class="column no-wrap flex-center"
              >
                <q-icon name="layers" size="36px" />
                <div class="q-mt-md text-center">
                  {{ lorem }}
                </div>
              </q-carousel-slide>
            </q-carousel>
          </div>
        </q-card>
      </div>
    </div>
    <q-toolbar>
      <div class="text-overline">Events</div>
      <q-space></q-space>

      <div class="text-overline">Your patients today</div>
      <div class="text-caption text-green q-ml-md">All patients</div>
      <q-icon
        name="fas fa-chevron-right"
        size="10px"
        class=""
        color="green-7"
      />
    </q-toolbar>
    <div class="row q-col-gutter-md">
      <div class="col-6">
        <q-card class="card1 q-mx-md q-pa-sm" bordered>
          <div class="row q-col-gutter-md">
            <div class="col-6">
              <div class="text-caption">Team meeting</div>
              <div class="text-caption text-grey-5">13:30 - 14:30</div>
              <div>
                <q-avatar
                  v-for="n in 5"
                  :key="n"
                  size="40px"
                  class="overlapping"
                  :style="`left: ${n * 25}px`"
                >
                  <img :src="`https://cdn.quasar.dev/img/avatar${n + 1}.jpg`" />
                </q-avatar>
              </div>
            </div>
            <div class="col-6">
              <div class="flex justify-end row">
                <q-toggle color="green" v-model="selection" val="green" />
              </div>
              <div class="flex justify-end row">
                <q-btn
                  round
                  icon="fas fa-pencil-alt"
                  size="10px"
                  color="black"
                  class="q-mr-sm"
                ></q-btn>
                <q-btn
                  round
                  icon="fas fa-chevron-right"
                  size="10px"
                  color="green"
                ></q-btn>
              </div>
            </div>
          </div>
        </q-card>
        <q-card class="card1 q-mx-md q-pa-sm q-mt-sm" bordered>
          <div class="row q-col-gutter-md">
            <div class="col-6">
              <div class="text-caption">Nobel prize</div>
              <div class="text-caption text-grey-5">13:30 - 14:30</div>
              <div>
                <q-avatar
                  v-for="n in 5"
                  :key="n"
                  size="40px"
                  class="overlapping"
                  :style="`left: ${n * 25}px`"
                >
                  <img :src="`https://cdn.quasar.dev/img/avatar${n + 1}.jpg`" />
                </q-avatar>
              </div>
            </div>
            <div class="col-6">
              <div class="flex justify-end row">
                <q-toggle color="gre" v-model="selection" val="" />
              </div>
              <div class="flex justify-end row">
                <q-btn
                  round
                  icon="fas fa-pencil-alt"
                  size="10px"
                  color="black"
                  class="q-mr-sm"
                ></q-btn>
                <q-btn
                  round
                  icon="fas fa-chevron-right"
                  size="10px"
                  color="green"
                ></q-btn>
              </div>
            </div>
          </div>
        </q-card>
      </div>
      <div class="col-6">
        <q-card class="q-mx-md q-pa-sm" bordered>
          <div class="row q-col-gutter-md">
            <div class="col-3">
              <div class="text-caption text-weight-bolder q-mt-lg">
                10:00 am
              </div>
            </div>
            <div class="col-9">
              <q-card class="q-px-sm colorCard" bordered flat>
                <q-item>
                  <q-item-section avatar>
                    <q-avatar>
                      <img src="https://cdn.quasar.dev/img/avatar2.jpg" />
                    </q-avatar>
                  </q-item-section>

                  <q-item-section>
                    <q-item-label>Sarah Hosten</q-item-label>
                    <q-item-label caption>Diagnosis: Stroke</q-item-label>
                  </q-item-section>
                  <q-item-section side>
                    <q-icon name="fas fa-ellipsis-v" color="" />
                  </q-item-section>
                </q-item>
              </q-card>
            </div>
          </div>
          <div class="row q-col-gutter-md q-mt-md">
            <div class="col-3">
              <div class="text-caption text-weight-bolder q-mt-lg">
                10:00 am
              </div>
            </div>
            <div class="col-9">
              <q-card class="q-px-sm colorCard" bordered flat>
                <q-item>
                  <q-item-section avatar>
                    <q-avatar>
                      <img src="https://cdn.quasar.dev/img/avatar2.jpg" />
                    </q-avatar>
                  </q-item-section>

                  <q-item-section>
                    <q-item-label>Sarah Hosten</q-item-label>
                    <q-item-label caption>Diagnosis: Stroke</q-item-label>
                  </q-item-section>
                  <q-item-section side>
                    <q-icon name="fas fa-ellipsis-v" color="" />
                  </q-item-section>
                </q-item>
              </q-card>
            </div>
          </div>
        </q-card>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from "vue";
// import { shuffle } from "lodash";

export default {
  name: "HomeView",
  components: {},

  setup() {
    return {
      slide: ref("style"),
      lorem: "Lorem ipsum dolor, sit amet consectetur adipi.",
      selection: ref(["green"]),
    };
  },
};
</script>
<style scoped>
.search {
  width: 700px;
}
.doctors {
  height: 220px;
}
.overlapping {
  border: 2px solid white;
  position: absolute;
  margin-left: -20px;
}
.card1 {
  height: 100px;
}
.top {
  margin-top: -40px;
}
.colorCard {
  background: #f8f8f8;
}
</style>
