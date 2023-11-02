# KCB-Mods
This repository is where the KCB Mods code is stored.

The code presented below is the main.js file for our website. It holds the functionality of our website.

import wixData from 'wix-data';

let debounceTimer;

export function Search_keyPress(event) { //enable onKeypress for input form

$w("#clearSearch").show();

$w("#Search").value;

    if (debounceTimer) {
        clearTimeout(debounceTimer);
        debounceTimer = undefined;
    }
    debounceTimer = setTimeout(() => {
        filter($w("#Search").value); //ID of input form
    }, 200);

}

let searchWord;

function filter(search) {
    if (searchWord !== search) {
        $w("#dataset1").setFilter(wixData.filter().contains('title', search)); // ID of the dataset
        searchWord = search;
    }

}
