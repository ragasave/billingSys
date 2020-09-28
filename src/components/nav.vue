<template>
    <div class="position-fixed w-100" style="z-index:999;top: 0px;">
        <!--Navbar-->
        <nav class="navbar navbar-expand-lg navbar-dark primary-color">

        <!-- Navbar brand -->
        <div>
            <div class="navbar-brand" href="#">Virustech SysBilling</div>
        </div>
        <!-- Collapse button -->
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#basicExampleNav"
            aria-controls="basicExampleNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <!-- Collapsible content -->
        <div class="collapse navbar-collapse justify-content-end" id="basicExampleNav">

            <!-- Links -->
            <ul class="navbar-nav">
            <li class="nav-item">
                <button class="print-btn btn btn-primary px-2 shadow-none">
                      <i class="fas fa-magic ml-1"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-printer"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg></i>
                </button>
                <button class="download-btn btn btn-primary px-2 shadow-none">
                    <i class="fas fa-magic ml-1"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-download"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path><polyline points="7 10 12 15 17 10"></polyline><line x1="12" y1="15" x2="12" y2="3"></line></svg></i>
                </button>
            </li>

            </ul>
        </div>
        <!-- Collapsible content -->

        </nav>
        <!--/.Navbar-->
    </div>
</template>
<script>
export default {
    
}
</script>