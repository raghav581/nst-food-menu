# Tasks

- [ ] Viewer
  - [ ] Show current week menu
- [ ] Admin
  - [ ] Log In
  - [ ] Add new menu as templates
  - [ ] Edit existing menu
  - [ ] Delete menu
  - [ ] Publish menu for current week

Pages:

- [ ] 1. MenuPage - shows current week menu
- [ ] 2. AdminPage - for admin tasks
  - [ ] 2.1 List of menus
    - [ ] 2.1.1 Edit button
    - [ ] 2.1.2 Delete button
    - [ ] 2.1.3 Add New Menu button
    - [ ] 2.1.4 Publish button
  - [ ] 2.2 EditMenuPage - for editing/adding menu
- [ ] 3. LoginPage - for admin login

API Endpoints:

- [ ] `/api/login` - POST - for admin login
- [ ] `/api/menus` - GET - get list of menus
- [ ] `/api/menus` - POST - add new menu
- [ ] `/api/menus/:id` - PUT - edit existing menu
- [ ] `/api/menus/:id` - DELETE - delete menu
- [ ] `/api/menus/:id/publish` - POST - publish menu for current week
- [ ] `/api/menus/current` - GET - get current week menu

Database Schema:

```js
const MenuSchema = {
  id: string
  label: string
  weekStartDate: Date
  weekEndDate: Date
  items: [
    {
      date: Date
      breakfast: [string]
      lunch: [string]
      snacks: [string]
      dinner: [string]
    }
  ]
  isPublished: boolean
}
```