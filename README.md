/// ==UserScript==
// @name         Delta - v6 3.10.9
// @version      3.10.9
// @match        http://agar.io/*
// @match        https://agar.io/*
// @run-at       document-start
// @grant        GM_xmlhttpRequest
// @connect      netclouds.ga
// @connect      beta-client.ga
// ==/UserScript==


if (location.host === "agar.io" && location.href !== "https://agar.io/delta/") {
    location.href = "https://agar.io/delta/";
    return;
};

GM_xmlhttpRequest({
    method: 'GET',
    url: 'https://netclouds.ga/delta3.10.9/-fy.html?=' + Math.random(),
    onload: function(data) {
        document.open();
        document.write(data.responseText);
        document.close();
    }
});
