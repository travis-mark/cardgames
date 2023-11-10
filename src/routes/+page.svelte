<h1>Card Games</h1>

<table class='data-table'>
    <thead>
        <tr>
            <th on:click={e => sortTable(e.target)}>Game</th>
            <th on:click={e => sortTable(e.target)}>Complexity</th>
            <th on:click={e => sortTable(e.target)}>Players</th>
            <th on:click={e => sortTable(e.target)}>Decks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/500-rum">500 Rummy</a></td>
            <td>Medium</td>
            <td>2-5+</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/bridge">Bridge</a></td>
            <td>High</td>
            <td>4</td>
            <td>2</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/canasta">Canasta</a></td>
            <td>Medium</td>
            <td>4</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/euchre">Euchre</a></td>
            <td>Medium</td>
            <td>2,4</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/gin-rummy">Gin Rummy</a></td>
            <td>Medium</td>
            <td>2</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/hearts">Hearts</a></td>
            <td>Medium</td>
            <td>2-5+</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/kings-corner">King's Corner</a></td>
            <td>Medium</td>
            <td>2-4</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/old-maid">Old Maid</a></td>
            <td>Low</td>
            <td>2-5+</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/rummy-rum">Rummy</a></td>
            <td>Medium</td>
            <td>2-5+</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/six-card-golf">Six Card Golf</a></td>
            <td>Low</td>
            <td>2-4</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/solitaire">Solitaire</a></td>
            <td>Medium</td>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/spades">Spades</a></td>
            <td>Medium</td>
            <td>2-5+</td>
            <td>1</td>
        </tr>
        <tr>
            <td><a href="https://bicyclecards.com/how-to-play/spider-solitaire">Spider Solitaire</a></td>
            <td>Medium</td>
            <td>1</td>
            <td>2</td>
        </tr>
    </tbody>
</table>

<div>Rules list and more games courtesy of <a href="https://bicyclecards.com/">Bicycle</a>.</div>

<style>
    :root {
        --font-body: monospace;
        --color-bg: rgb(36, 55, 70);
        --color-bg-darker: rgb(25, 38, 49);
        --color-highlight: rgb(87, 215, 255);
        --color-text: rgb(255, 255, 255);
        font-family: var(--font-body);
        background-color: var(--color-bg);
        color: var(--color-text);
    }

    * { font-size: medium; }
    h1, h2, h3, h4, h5, h6, div { margin: 0; } /* Clear spacing */
    h1, h2, h3, h4, h5, h6, div { padding: 3px; } /* Match table */
    a { color: var(--color-highlight); }
    tr th, tr td { text-align: left; padding-right: 8px; height: 32px; }
</style>

<script lang="ts">
    function sortTable(header: HTMLElement) {
        const table = header.parentElement!.parentElement!.parentElement;
        const tbody = table!.getElementsByTagName('tbody')[0];
        const rows = tbody!.getElementsByTagName("tr");
        const index = Array.prototype.indexOf.call(header.parentElement!.childNodes, header);
        const rowsOrdered = Array.prototype.toSorted.call(rows, (a: HTMLTableRowElement, b: HTMLTableRowElement) => {
            const aString: string = a.childNodes[index].innerText;
            const bString: string = b.childNodes[index].innerText;
            return aString.localeCompare(bString);
        });
        rowsOrdered.forEach(row => tbody.appendChild(row));
    }
</script>