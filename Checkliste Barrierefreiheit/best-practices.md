## title-Attribut

````html
<a title="Toller Hinweistext" href="#">Linktext</a>
````

````html
    <img src="#" alt="Wein vor einem Fass" title="Wein vor einem Fass (Foto: Adobe Stock)">  
````

````html
<iframe
  id="inlineFrameExample"
  title="Open StreetMap"
  width="300"
  height="200"
  src="https://www.openstreetmap.org/.....">
</iframe>
````

````html

````
## aria-label

````html
<button id="mobile-toggle" class="nav-button" aria-expanded="false" aria-controls="mobile-menu" aria-label="Navigation öffnen">Menü</button>
````

````html

````

````html

````

````html

````


## aria-describedby


````html

````

````html

````

````html

````

````html

````


## aria-hidden


````html
<input 
    type="file"
    className="sr-only"
    aria-hidden="true"
    tabIndex={-1}
/>
````

````html

````

````html

````

````html

````

## sr-only bzw.visuallyhidden

Bei mehreren Infos, die zusammengefasst werden sollen und eventuell auch durch einen optionalen Text ergänzt werden sollen, kann es sich anbieten, alle Infos doppelt in den Code zu schreiben, aber nicht visuell darzustellen.

````html
<a href="#">
    <span aria-hidden="true">
        <span>Fr.</span>
        <span>5.9.</span>
    </span>
    <span class="sr-only" data-testid="accName">Fr., 5.9., regnerisch</span>
    <svg aria-hidden="true" aria-label="Icon"></svg>
</a>
````

## Buttons (unterschiedliche Fälle)

````html
<button type="button" aria-label="Edit">
    <svg aria-hidden="true" aria-label="Icon" data-testid="icon-svg" fill="currentColor" height="24" viewBox="0 0 24 24"
        width="24" xmlns="http://www.w3.org/2000/svg">
        <path fill="currentColor"
            d="m20.72 5.57-2.28-2.28a1.015 1.015 0 0 0-1.43.01L4.77 15.54 2.99 21l5.46-1.77L20.71 6.99c.4-.39.4-1.03.01-1.42m-2.98-.86 1.57 1.57-.95.95-1.57-1.57zM6.71 15.72l9.01-9 1.57 1.57-9.02 9-1.56-1.56zM5.87 17l1.12 1.12-1.66.54z">
        </path>
    </svg>
</button>
````

````html
<button type="button">
    <svg aria-hidden="true" data-testid="icon-svg" fill="currentColor" height="24" viewBox="0 0 24 24" width="24"
        xmlns="http://www.w3.org/2000/svg">
        <path fill="currentColor"
            d="m20.72 5.57-2.28-2.28a1.015 1.015 0 0 0-1.43.01L4.77 15.54 2.99 21l5.46-1.77L20.71 6.99c.4-.39.4-1.03.01-1.42m-2.98-.86 1.57 1.57-.95.95-1.57-1.57zM6.71 15.72l9.01-9 1.57 1.57-9.02 9-1.56-1.56zM5.87 17l1.12 1.12-1.66.54z">
        </path>
    </svg>
    <span class="sr-only">Edit</span>
</button>
````

````html
<button aria-label="nach oben" type="button">
    <span>
        <span>
            <span aria-hidden="true">
                <svg aria-hidden="true" aria-label="Icon" data-testid="icon-svg" fill="currentColor" height="24"
                    viewBox="0 0 24 24" width="24" xmlns="http://www.w3.org/2000/svg">
                    <path fill="currentColor" fill-rule="evenodd"
                        d="m12 8.5 6 5.879-1.145 1.121L12 10.743 7.144 15.5 6 14.379z" clip-rule="evenodd"></path>
                </svg>
            </span>
            <span>nach oben</span>
        </span>
    </span>
</button>
````
