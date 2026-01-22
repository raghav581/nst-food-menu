<template>
  <q-page class="q-pa-md">
    <q-markup-table>
      <thead>
        <tr>
          <th>Day</th>
          <th>
            Monday <br />
            {{ currentMenu[0]?.date || 'N/A' }}
          </th>
          <th>
            Tuesday <br />
            {{ currentMenu[1]?.date || 'N/A' }}
          </th>
          <th>
            Wednesday <br />
            {{ currentMenu[2]?.date || 'N/A' }}
          </th>
          <th>
            Thursday <br />
            {{ currentMenu[3]?.date || 'N/A' }}
          </th>
          <th>
            Friday <br />
            {{ currentMenu[4]?.date || 'N/A' }}
          </th>
          <th>
            Saturday <br />
            {{ currentMenu[5]?.date || 'N/A' }}
          </th>
          <th>
            Sunday <br />
            {{ currentMenu[6]?.date || 'N/A' }}
          </th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <td>Breakfast</td>
          <td>{{ currentMenu[0]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[1]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[2]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[3]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[4]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[5]?.breakfast || 'N/A' }}</td>
          <td>{{ currentMenu[6]?.breakfast || 'N/A' }}</td>
        </tr>

        <tr>
          <td>Lunch</td>
          <td>{{ currentMenu[0]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[1]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[2]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[3]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[4]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[5]?.lunch || 'N/A' }}</td>
          <td>{{ currentMenu[6]?.lunch || 'N/A' }}</td>
        </tr>

        <tr>
          <td>Snacks</td>
          <td>{{ currentMenu[0]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[1]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[2]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[3]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[4]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[5]?.snacks || 'N/A' }}</td>
          <td>{{ currentMenu[6]?.snacks || 'N/A' }}</td>
        </tr>

        <tr>
          <td>Dinner</td>
          <td>{{ currentMenu[0]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[1]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[2]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[3]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[4]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[5]?.dinner || 'N/A' }}</td>
          <td>{{ currentMenu[6]?.dinner || 'N/A' }}</td>
        </tr>
      </tbody>
    </q-markup-table>
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

    return {
      currentMenu,
    }
  },
})
</script>
