vue hackernews 2 0 hackernews clone built with vue 2 0 vue router vuex with server side rendering live demo features note in practice it is unnecessary to code split for an app of this size where each async chunk is only a few kilobytes nor is it optimal to extract an extra css file which is only 1kb they are used simply because this is a demo app showcasing all the supported features in real apps you should always measure and optimize based on your actual app constraints server side rendering vue vue router vuex working together server side data pre fetching client side state dom hydration automatically inlines css used by rendered components only preload prefetch resource hints route level code splitting progressive web app app manifest service worker 100 100 lighthouse score single file vue components hot reload in development css extraction for production animation effects when switching route views real time list updates with flip animation architecture overview a detailed vue ssr guide can be found here build setup requires node js 7 bash install dependencies npm install or yarn serve in dev mode with hot reload at localhost 8080 npm run dev build for production npm run build serve in production mode npm start license mit