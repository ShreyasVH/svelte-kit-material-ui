<script>
    import DataTable, { Head, Body, Row, Cell } from '@smui/data-table';

    const columns = [
        'Country',
        'Capital',
        'Currency',
        'Continent'
    ];

    const data = [
        {
            country: 'India',
            capital: 'New Delhi',
            currency: 'Rupee',
            continent: 'Asia'
        },
        {
            country: 'United Kingdom',
            capital: 'London',
            currency: 'Pound',
            continent: 'Europe'
        }
    ];
</script>

<div>
    <DataTable style="width: 100%">
        <Head>
            <Row>
                {#each columns as column}
                    <Cell head>
                        {column}
                    </Cell>
                {/each}
            </Row>
        </Head>

        <Body>
            {#each data as row}
                <Row>
                    {#each columns as column}
                    <Cell>
                        {row[column.toLowerCase()]}
                    </Cell>
                    {/each}
                </Row>
            {/each}
        </Body>
    </DataTable>
</div>