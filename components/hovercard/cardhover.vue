<template>
  <v-row class="mt-4 pl-6">
    <v-col cols="12" sm="2" md="3" v-for="(item, index) in items" :key="index">
      <v-card
        class="item mb-12 mt-12"
        target="_blank"
        @mouseover="currentIndex = index"
        @mouseleave="currentIndex = null"
      >
        <div class="img-border">
          <img :src="item.imageUrl" alt="" />
        </div>
        <div class="detail" v-show="currentIndex === index">
          <div class="detail-button">
            <v-row md="4" class="detail-button-left justify-space-around mt-2">
              <v-btn><v-icon>mdi-play</v-icon></v-btn>
              <v-btn><v-icon>mdi-plus</v-icon></v-btn>
              <v-btn><v-icon>mdi-thumb-up</v-icon></v-btn>
            </v-row>
          </div>
          <div class="detail-rating mt-2">
            <p>ตรงกัน 95%</p>
            <p>18+</p>
            <p>5 ซีซั่น</p>
          </div>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  data() {
    return {
      currentIndex: null,
      items: [
        {
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
      ],
    }
  },
}
</script>

<style scoped>
.item {
  width: 350px;
  height: 200px;
  margin: 0 5px;
  transition: 0.3s ease;
}
.img-border {
  width: 350px;
  height: 200px;
}
.item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.item:hover {
  transform: scale(1.2);
}
.detail {
  display: flex;
  flex-direction: column;
  padding: 10px;
}
.detail-button {
  justify-content: space-between;
  margin-bottom: 10px;
}
.detail-button-left v-btn,
.detail-button-right v-btn {
  width: 50px;
  height: 50px;
}
.detail-button-left v-btn:first-child {
  background-color: #fff;
  color: #333;
  border: none;
}
.detail-button-left v-btn:last-child {
  transform: rotate(180deg);
}
.detail-button-right v-btn {
  transform: rotate(90deg);
}
.detail-rating {
  display: flex;
}
.detail-rating p {
  margin-right: 10px;
}
.detail-rating p:first-child {
  color: #2ecc71;
  font-weight: bold;
}
.detail-rating p:nth-child(2) {
  border: 1px solid #fff;
  padding: 0 5px;
}
</style>
