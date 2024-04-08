<template>
    <div class="bg-blue-300 rounded-xl mx-auto p-2 shadow mb-2">
        <p>home status</p>
        <div class="flex">
            <div class="mr-2">
                <div class="p-1 bg-slate-200 rounded shadow-md mb-2 grid  grid-cols-2 gap-1 text-xs">
                    <div>
                        <p>temperature</p>
                    </div>
                    <div>
                        0
                    </div>
                    <div>
                        <p>humidity</p>
                    </div>
                    <div>
                        0
                    </div>
                    <div>
                        <p>fog</p>
                    </div>
                    <div>
                        0
                    </div>
                </div>
                <div class="p-1 bg-slate-200 rounded shadow-md text-xs">
                    <p class="bg-slate-200 text-center">internet traffic</p>
                    <div class="rounded bg-slate-300 p-1 m-1">
                        <div class="flex">
                            <svg width="20" height="20" viewBox="0 0 40 41" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <use xlink:href="../assets/images/operators/operators.svg#megafon" />
                            </svg>- 
                            <a href="" class="text-green-600">89248986280</a>
                        </div>
                        <div class="flex justify-between">
                            <span>31.10.2020</span>
                            <span>600 Р</span>
                        </div>
                    </div>
                    <div class="rounded bg-slate-300 p-1 m-1">
                        <div class="flex">
                            <svg width="20" height="20" viewBox="0 0 40 41" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <use xlink:href="../assets/images/operators/operators.svg#mts" />
                            </svg>- 
                            <a href="" class="text-red-500">89142364278</a>
                        </div>
                        <div class="flex justify-between">
                            <span>27/10/10</span>
                            <span>250 r</span>
                        </div>
                    </div>
                    <div class="rounded bg-slate-300 p-1 m-1">
                        <div class="flex">
                            <svg width="20" height="20" viewBox="0 0 40 41" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <use xlink:href="../assets/images/operators/operators.svg#beeline" />
                            </svg>- 
                            <a href="" class="text-yellow-600">89681501976</a>
                        </div>
                        <div class="flex justify-between">
                            <span>27/10/10</span>
                            <span>200 r</span>
                        </div>
                    </div>

                </div>
            </div>
            <div class="p-1 bg-slate-200 rounded shadow-md w-full">
                <p>camera data</p>
                <p>20.20.20 г.</p>
                <div class="m-1">
                    <div class="flex mt-2">
                        <div class="bg-black w-12 h-8 mr-1">
                            <img src="../C:/Users/Professional/IdeaProjects/PixelDetect1.2/asssets/screenshots/all-screens/5114631873545535939.bmp" alt="">
                        </div>
                        door
                    </div>
                    <div class="flex mt-2">
                        <div class="bg-black w-12 h-8 mr-1">

                        </div>
                        garage
                    </div>
                    <div class="flex mt-2">
                        <div class="bg-black w-12 h-8 mr-1">

                        </div>
                        inside
                    </div>
                    <div class="flex mt-2">
                        <div class="bg-black w-12 h-8 mr-1">

                        </div>
                        street
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>