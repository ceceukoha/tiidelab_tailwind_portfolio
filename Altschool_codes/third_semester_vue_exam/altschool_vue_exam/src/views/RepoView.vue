

<template>
    <div class="repo-page">
        <h1>Welcome to the Git Repository Storage Box!</h1>

        <p>Manage your Repository on the go! This section contains all of your project's files and each file's revision
            history!</p>

        <div class="pagination">
            <button @click="prevHandle()">Prev</button>
            <div v-for="num in pages">
                <button @click="skipHandle(num)" :class="page === num ? 'currPage' : ''">{{ num }}</button>
            </div>
            <button @click="nextHandle()">Next</button>
        </div>

        <div>
            <h1>Search</h1>
            <form class="d-flex mx-auto" role="search">
                <input class="form-control me-1 w-25 m-auto" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>


        <div v-if="isLoading">
            <h1>Loading...</h1>
            <div class="d-flex justify-content-center">
                <div class="spinner-border" role="status">
                    <span class="visually-hidden">Loading...</span>
                </div>
            </div>
        </div>
        <div v-else class="ret-items">
            <div v-for="repo in repos " :key="repo.id">
                <div class="card d-flex justify-content-center mx-auto pt-5 mt-5" style="width: 28rem;">
                    <img src="..." class="card-img-top" alt="...">
                    <div class="card-body">
                        <h1 class="card-title">Repo Name</h1>
                        <p class="card-text">{{ repo.name }}</p>
                        <ul class="list-group list-group-flush">
                            <li class="list-group-item">Visibility: {{ repo.visibility }}</li>
                            <li class="list-group-item">Copy Url: {{ repo.clone_url }}</li>
                            <li class="list-group-item">A third item</li>
                        </ul>
                        <RouterLink to="/{{repo.}}" href="#" class="btn btn-primary">Visit Repo</RouterLink>
                    </div>
                </div>
                <p>Name of Repository</p>

                <h2>

                    {{ repo.name }}
                </h2>
                <p>Link to Repository</p>
                <h3>
                    {{ repo.url }}
                </h3>
            </div>
        </div>

    </div>
</template>


<style>
.repo-page {
    padding: 30px;
    background-color: #fff;
}

.repo-page h1 {
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    text-align: center;
}

.repo-page p {
    margin-top: 30px;
    font-size: 20px;
    text-align: center;
}

.ret-items h2 {
    font-size: 12px;
}

.pagination {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
}

.pagination button {
    padding: 1em;
    background-color: rgb(33, 37, 30);
    border: none;
    color: white;
    border-radius: 5px;
}
</style>


<script>
export default {
    data() {
        return {
            repos: [],
            isLoading: true
        }
    },
    computed: {
    pages: function () {
      return [this.page, this.page + 1, this.page + 2, this.page + 3]
    }
  },
    mounted() {
        this.fetchRepo();
    },
    methods: {
        fetchRepo() {
            fetch('https://api.github.com/users/ceceukoha/repos')
                .then((response) => {
                    return response.json()
                })
                .then((data) => {
                    this.repos = data
                    this.isLoading = false
                    // console.log(data)
                })


        }
        , nextHandle() {
            this.page = this.page + 1
            this.selectUser()
        },

        skipHandle(num) {
            this.page = num
            this.selectUser()
        },

        prevHandle() {
            if (this.page > 1) {
                this.page = this.page - 1
                this.selectUser()
            }
        }
    }

}
</script>