<template>
  <q-page class="q-pa-md">
    <q-markup-table flat bordered>
      <thead>
        <tr>
          <th>Day</th>
          <th>
            Monday <br />
            <q-input
              v-model="currentMenu[0].date"
              outlined
              dense
              @update:model-value="() => handleDateChange(0)"
            >
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[0].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                      @update:model-value="() => handleDateChange(0)"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Tuesday <br />
            <q-input v-model="currentMenu[1].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[1].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Wednesday <br />
            <q-input v-model="currentMenu[2].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[2].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Thursday <br />
            <q-input v-model="currentMenu[3].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[3].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Friday <br />
            <q-input v-model="currentMenu[4].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[4].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Saturday <br />
            <q-input v-model="currentMenu[5].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[5].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
          <th>
            Sunday <br />
            <q-input v-model="currentMenu[6].date" outlined dense>
              <template #append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                    <q-date
                      v-model="currentMenu[6].date"
                      mask="YYYY-MM-DD"
                      title="Select Date"
                      today-button="Today"
                    >
                      <div class="row items-center justify-end">
                        <q-btn v-close-popup label="Close" color="primary" flat />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <td>Breakfast</td>
          <td><q-input type="textarea" v-model="currentMenu[0].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[1].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[2].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[3].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[4].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[5].breakfast" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[6].breakfast" outlined dense /></td>
        </tr>

        <tr>
          <td>Lunch</td>
          <td><q-input type="textarea" v-model="currentMenu[0].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[1].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[2].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[3].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[4].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[5].lunch" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[6].lunch" outlined dense /></td>
        </tr>

        <tr>
          <td>Snacks</td>
          <td><q-input type="textarea" v-model="currentMenu[0].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[1].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[2].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[3].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[4].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[5].snacks" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[6].snacks" outlined dense /></td>
        </tr>

        <tr>
          <td>Dinner</td>
          <td><q-input type="textarea" v-model="currentMenu[0].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[1].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[2].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[3].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[4].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[5].dinner" outlined dense /></td>
          <td><q-input type="textarea" v-model="currentMenu[6].dinner" outlined dense /></td>
        </tr>
      </tbody>
    </q-markup-table>

    <q-btn label="Save Menu" color="primary" class="q-mt-md" @click="saveMenu" push />
  </q-page>
</template>

<script>
import { defineComponent, ref, onMounted } from 'vue'
import { api } from 'boot/axios'

export default defineComponent({
  name: 'IndexPage',

  setup() {
    const currentMenu = ref([
      {
        date: '2026-01-26',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-01-27',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-01-28',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-01-29',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-01-30',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-01-31',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
      {
        date: '2026-02-01',
        breakfast: 'Pancakes, Fruit Salad',
        lunch: 'Dal, Rice, Veggies',
        snacks: 'Cookies, Tea',
        dinner: 'Paneer Tikka, Naan',
      },
    ])

    function fetchMenu() {
      api
        .get('/menu/current-week')
        .then((response) => {
          currentMenu.value = response.data
        })
        .catch((error) => {
          console.error('Error fetching menu:', error)
        })
    }

    onMounted(() => {
      fetchMenu()
    })

    // update all other dates when we set the first date
    function setDatesFromFirst() {
      const firstDate = new Date(currentMenu.value[0].date)
      for (let i = 1; i < currentMenu.value.length; i++) {
        const newDate = new Date(firstDate)
        newDate.setDate(firstDate.getDate() + i)
        const year = newDate.getFullYear()
        const month = String(newDate.getMonth() + 1).padStart(2, '0')
        const day = String(newDate.getDate()).padStart(2, '0')
        currentMenu.value[i].date = `${year}-${month}-${day}`
      }
    }

    function handleDateChange(index) {
      if (index === 0) {
        setDatesFromFirst()
      }
    }

    return {
      currentMenu,
      handleDateChange,
    }
  },
})
</script>
