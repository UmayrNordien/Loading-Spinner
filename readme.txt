Will be used for EOM + Capstone Projects via

npm install --save vue-loading-overlay

import Loading from 'vue-loading-overlay';
import 'vue-loading-overlay/dist/vue-loading.css';

export default {
  components: {
    Loading,
  },
  data() {
    return {
      isLoading: false,
      data: null,
    };
  },
  methods: {
    fetchData() {
      this.isLoading = true;

      fetch('https://api.example.com/data')
        .then((response) => response.json())
        .then((data) => {
          this.data = data;
        })
        .finally(() => {
          this.isLoading = false;
        });
    },
  },
};
