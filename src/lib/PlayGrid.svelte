<script>
  const initialGrid = [
    "xxx85xxxx",
    "xx3xx9xxx",
    "x58xx72xx",
    "5xx24xx1x",
    "9xx13xx7x",
    "x26xx843x",
    "xx2xx1xx6",
    "xxx563xx9",
    "xxxxxx38x",
  ];

  import { onMount } from "svelte";

  import Cell from "./Cell.svelte";

  let mainGrid = [];
  const GRID_SIZE = 9;
  function _initGrid() {
    for (let i = 0; i < GRID_SIZE; i++) {
      mainGrid = [
        ...mainGrid,
        {
          row: i,
          row_content: [],
        },
      ];
      for (let j = 0; j < GRID_SIZE; j++) {
        mainGrid[i].row_content = [
          ...mainGrid[i].row_content,
          {
            row: i,
            col: j,
            key: i + "," + j,
            content:
              initialGrid[i].charAt(j) === "x" ? "" : initialGrid[i].charAt(j),
            locked: initialGrid[i].charAt(j) !== "x",
          },
        ];
      }
    }
    console.dir(mainGrid);
  }

  onMount(_initGrid);
</script>

<div class="mainGrid">
  {#each mainGrid as row (row.row)}
    {#each row.row_content as cell (cell.key)}
      <Cell content={cell.content} locked={cell.locked} />
    {/each}
  {/each}
</div>

<style>
  .mainGrid {
    display: grid;
    grid-template-columns: repeat(9, 1fr);
  }
</style>
