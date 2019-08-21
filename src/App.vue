<template>
    <div id="app">
        <!--        <h1> {{nome}}</h1>-->
        <!--        <p> {{nome2}}</p>-->
        <!--        <p v-if="(nome2 > 1)"> Escondido </p>-->
        <!--        <p v-else> tette </p>-->

        <!--        <table>-->
        <!--            <tr v-for="pessoa in pessoas">-->
        <!--                <td>{{pessoa.id}}</td>-->
        <!--                <td>{{pessoa.nome}}</td>-->
        <!--            </tr>-->
        <!--        </table>-->
        <!--        <label>-->
        <!--            <input v-model="nome" @change="mudaNome">-->
        <!--        </label>-->
        <!-- Page Wrapper -->
        <div id="wrapper">
            <Sidebar></Sidebar>
            <router-view></router-view>
<!--            &lt;!&ndash; Content Wrapper &ndash;&gt;-->
<!--            <div id="content-wrapper" class="d-flex flex-column">-->
<!--                &lt;!&ndash; Main Content &ndash;&gt;-->
<!--                <div id="content">-->
<!--                    <Topbar></Topbar>-->
<!--                    <PageContent></PageContent>-->
<!--                </div>-->
<!--                &lt;!&ndash; End of Main Content &ndash;&gt;-->
<!--            </div>-->
<!--            &lt;!&ndash; End of Content Wrapper &ndash;&gt;-->

        </div>
<!--        &lt;!&ndash; End of Page Wrapper &ndash;&gt;-->
<!--        <Footer></Footer>-->
<!--        &lt;!&ndash; Scroll to Top Button&ndash;&gt;-->
<!--        <a class="scroll-to-top rounded" href="#page-top">-->
<!--            <i class="fas fa-angle-up"></i>-->
<!--        </a>-->

<!--        &lt;!&ndash; Logout Modal&ndash;&gt;-->
<!--        <div class="modal fade" id="logoutModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel"-->
<!--             aria-hidden="true">-->
<!--            <div class="modal-dialog" role="document">-->
<!--                <div class="modal-content">-->
<!--                    <div class="modal-header">-->
<!--                        <h5 class="modal-title" id="exampleModalLabel">Ready to Leave?</h5>-->
<!--                        <button class="close" type="button" data-dismiss="modal" aria-label="Close">-->
<!--                            <span aria-hidden="true">×</span>-->
<!--                        </button>-->
<!--                    </div>-->
<!--                    <div class="modal-body">Select "Logout" below if you are ready to end your current session.</div>-->
<!--                    <div class="modal-footer">-->
<!--                        <button class="btn btn-secondary" type="button" data-dismiss="modal">Cancel</button>-->
<!--                        <a class="btn btn-primary" href="login.html">Logout</a>-->
<!--                    </div>-->
<!--                </div>-->
<!--            </div>-->
<!--        </div>-->
    </div>
</template>

<script>
    import axios from "axios"
    import Footer from "./components/Footer";
    import PageContent from "./components/PageContent";
    import Sidebar from "./components/Sidebar";
    import Topbar from "./components/Topbar";

    export default {
        name: "App",
        components: {
            Footer,
            PageContent,
            Sidebar,
            Topbar
        },
        data: () => ({
            nome: "Pedro",
            nome2: 0,
            pessoas: [],
        }),
        methods: {
            mudaNome() {
                this.nome2 += 1;
            },
            getPessoa() {
                axios.get('HTTP://localhost:3000/info')
                    .then(result => {
                        this.pessoas = result.data
                    })
            }
        },
        mounted() {
            this.getPessoa()
        }
    }
</script>
<style>

</style>
