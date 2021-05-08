<template>
  <div class="navbar">
    <div class="navbar__logo">
      <img
        src="https://sf16-scmcdn-sg.ibytedtos.com/goofy/tiktok/web/node/_next/static/images/logo-whole-c555aa707602e714ec956ac96e9db366.svg"
        alt="logo tiktok"
      />
    </div>
    <div class="navbar__search">
      <NavbarSearch />
    </div>
    <div v-if="logged" class="navbar__account">
      <div class="navbar__icon icons">
        <img src="~/assets/icons/upload-icon.svg" alt="upload icon" />
      </div>
      <div class="navbar__icon icons">
        <img src="~/assets/icons/message-icon.svg" alt="message icon" />
      </div>
      <div class="navbar__icon icons">
        <img src="~/assets/icons/inbox-icon.svg" alt="inbox icon" />
      </div>
      <div class="navbar__setting icons">
        <div class="navbar__profile"></div>
        <div class="navbar__setting__sub">
          <ul class="navbar__setting__menu">
            <li>
              <div>
                <img src="~/assets/icons/profile-icon.svg" alt="profile icon" />
                <p>View Profile</p>
              </div>
            </li>
            <li>
              <div>
                <img src="~/assets/icons/gear-icon.svg" alt="settings icon" />
                <p>Settings</p>
              </div>
            </li>
            <li>
              <div>
                <img src="~/assets/icons/english-icon.svg" alt="english icon" />
                <p>English</p>
              </div>
            </li>
            <li>
              <div>
                <img src="~/assets/icons/privacy-icon.svg" alt="privacy icon" />
                <p>Feedback and help</p>
              </div>
            </li>
            <hr />
            <li>
              <div>
                <img src="~/assets/icons/privacy-icon.svg" alt="privacy icon" />
                <p>Logout</p>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div v-else class="navbar__account">
      <nuxt-link to="/" class="navbar__upload">Upload</nuxt-link>
      <button class="btn-primary">Log in</button>
      <div class="navbar__setting icons">
        <img src="~/assets/icons/setting-icon.svg" alt="setting icon" />
        <div class="navbar__setting__sub">
          <ul class="navbar__setting__menu">
            <li>
              <div>
                <img src="~/assets/icons/english-icon.svg" alt="english icon" />
                <p>English</p>
              </div>
            </li>
            <li>
              <div>
                <img src="~/assets/icons/privacy-icon.svg" alt="privacy icon" />
                <p>Feedback and help</p>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data: () => ({
    logged: true,
  }),
}
</script>

<style scped>
.navbar {
  width: 1060px;
  max-width: 1200px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Proxima';
  font-weight: normal;
}

.navbar__icon {
  position: relative;
}

.navbar__icon:hover::before {
  content: '';
  position: absolute;
  display: block;
  border: 1rem solid transparent;
  border-top: none;
  border-bottom-color: rgba(84, 84, 84, 1);
  bottom: -10px;
}

.navbar__icon:hover:nth-child(1)::after {
  content: 'Upload video';
  display: block;
}

.navbar__icon:hover:nth-child(2)::after {
  content: 'Message';
  display: block;
  width: 80px;
  left: -80%;
}

.navbar__icon:hover:nth-child(3)::after {
  content: 'Inbox';
  display: block;
  width: 60px;
  left: -60%;
}

.navbar__icon:nth-child(1)::after,
.navbar__icon:nth-child(2)::after,
.navbar__icon:nth-child(3)::after {
  position: absolute;
  display: none;
  width: 100px;
  background-color: rgba(84, 84, 84, 1);
  color: #fff;
  padding: 10px 5px;
  border-radius: 10px;
  text-align: center;
  font-size: 16px;
  left: -100%;
  top: 40px;
  font-weight: 600;
}

.navbar__profile {
  width: 32px;
  height: 32px;
  background-color: var(--black-color);
  border-radius: 50%;
  margin-right: -8px;
}

.navbar__account {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar__account > * {
  margin-left: 20px;
}

.navbar__search {
  width: 330px;
  padding: 14px 14px;
  margin-left: 40px;
  background-color: var(--darker-gray-color);
  border-radius: 50px;
}

.navbar__search:focus-within {
  border: 1px solid var(--silver-color);
}

.navbar__upload {
  font-family: 'Proxima';
  font-weight: 700;
  color: #000;
  text-decoration: none;
}

.navbar__upload:hover {
  text-decoration: underline;
}

.navbar__setting {
  position: relative;
}

.navbar__setting:hover .navbar__setting__sub {
  display: block;
}

.navbar__setting__sub {
  display: none;
  position: absolute;
  right: -80%;
  padding: 10px 0;
}

.navbar__setting__menu::before {
  content: '';
  position: absolute;
  display: block;
  right: 10px;
  top: -10px;
  border: 1rem solid transparent;
  border-top: none;
  border-bottom-color: #fff;
}

.navbar__setting__menu {
  position: relative;
  width: 200px;
  list-style: none;
  padding: 10px 0;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 1px 1px 18px 0 rgba(0, 0, 0, 0.1);
}

.navbar__setting__menu hr {
  border: 0.5px solid var(--darker-gray-color);
}

.navbar__setting__menu li {
  padding: 10px 10px;
  font-weight: normal;
  font-family: 'SofiaRegular';
}

.navbar__setting__menu li:hover {
  background-color: var(--gray-color);
}

.navbar__setting__menu li div {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.navbar__setting__menu li div p {
  margin-left: 10px;
}
</style>
