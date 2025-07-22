<script>
  import { onMount } from 'svelte';
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart as HighchartsSvelte } from "@highcharts/svelte";

  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";

  let chartOptions = null;

  onMount(async () => {
    const response = await fetch('/data/edu_07.json');
    const json = await response.json();
    const data = json.results;

    const years = [...new Set(data.map(d => d.year))].sort();
    const races = [...new Set(data.map(d => d.race))];

    const series = races.map(race => ({
      name: race,
      data: years.map(year => {
        const entry = data.find(d => d.race === race && d.year === year);
        return entry ? entry.pct_enrollment_undergrad : null;
      })
    }));

    chartOptions = {
      chart: {
        type: 'line'
      },
      title: {
        text: 'Undergraduate Degree Attainment by Race (2021–2023)'
      },
      xAxis: {
        categories: years,
        title: {
          text: 'Year'
        }
      },
      yAxis: {
        title: {
          text: 'Undergraduate Enrollment (%)'
        },
        min: 0
      },
      tooltip: {
        shared: true,
        valueSuffix: '%'
      },
      series
    };
  });
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <h1>We know there are problems in the education system, but what does the data say?</h1>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>The evidence provided by that data simply cannont be denied.</strong>
      </ArticleText>

      <ArticleText>
        <strong>The facts paint the picture.</strong> Inequities in education due to someones identity, affects them in their pursuit of higher education and ultimately their careers.
      </ArticleText>

      <ArticleText>
        <strong>Identity should not determine opportunity</strong><br /><br />
        When 
      </ArticleText>

      {/snippet}
  </Scroller>
</div>

{#if chartOptions}
  <HighchartsSvelte options={chartOptions} />
{:else}
  <p>Loading chart...</p>
{/if}
