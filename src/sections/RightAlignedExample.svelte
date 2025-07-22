<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let options = {
        chart: {
            type: "pie",
        },
        title: {
            text: "An Example Pie Chart",
        },
        plotOptions: {
            pie: {
                allowPointSelect: true,
                dataLabels: [
                    {
                        enabled: true,
                        distance: 20,
                    },
                    {
                        enabled: true,
                        distance: -40,
                        format: "{point.percentage:.1f}%",
                        style: {
                            fontSize: "1.2em",
                            textOutline: "none",
                        },
                        filter: {
                            operator: ">",
                            property: "percentage",
                            value: 10,
                        },
                    },
                ],
            },
        },
        series: [
            {
                name: "Group",
                data: [
                    {
                        name: "Group 1",
                        y: 151,
                    },
                    {
                        name: "Group 2",
                        sliced: true,
                        selected: true,
                        y: 180,
                    },
                    {
                        name: "Group 3",
                        y: 32,
                    },
                    {
                        name: "Group 4",
                        y: 103,
                    },
                    {
                        name: "Group 5",
                        y: 77,
                    },
                ],
            },
        ],
    };
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}

        <h1>We know there are problems in the education system, but what does the data say?</h1>
          
            <!-- <p>
                Here's an example chart using
                <a href="https://www.highcharts.com/">Highcharts</a>!
            </p>
            <p>
                📈 <strong>Highcharts</strong> is a super-flexible library for
                creating all kinds of charts. See demos of different chart types
                <a href="https://www.highcharts.com/demo">here</a>.
            </p>
            <p>
                Since we're using Highcharts through Svelte, the syntax is a
                little different from what you might see in the demos. But all
                of Highcharts' functionality is available through the Highcharts
                for Svelte package.
            </p>
            <p>
                The configuration is done through the
                <code>options</code> json object passed to the chart, which you'll
                see in the source code for this template.
            </p>
            <p>
                Use the
                <a href="https://api.highcharts.com/highcharts/"
                    >API reference</a
                >
                to understand what each element in the <code>options</code> object
                does. -->
            <!-- </p> -->
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>Is education in the United States really fair?!</strong
                >
            </ArticleText>

            <ArticleText>
               <strong>Inequality starts early. </strong> Access to early childhood education varies greatly across socio-economic groups and especially affects students of color. Children in underresourced schools often start behind and remain behind.
            </ArticleText>

            <ArticleText>
                <strong>Resources Shape Outcomes</strong>
                <br /><br />
                    Schools in affluent and less diverse areas often have newer facilities, better technology, and more extracurricular opportunities than schools in underserved communities.

            </ArticleText>

            <ArticleText>
                 <strong>Quality education depends on quality teachers.</strong> 
                <br /><br />
               
Underfunded schools across the country struggle to attract and retain experienced educators.              
            </ArticleText>
        {/snippet}
    </Scroller>
</div>


