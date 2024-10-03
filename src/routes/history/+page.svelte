<script lang="ts">
    import { Table } from '@sveltestrap/sveltestrap';
    const request = fetch('https://db.rhysmason.uk/api/v2/tables/mmajcep1y0ye0jm/records', {
      method: "GET",
      headers: {
        "content-type": "application/json",
        'xc-token': "Q8YZuXP7WkAUPFE9-ZnpQ_AAXQ-8JdLPeFAitgDI"
      }
    });
  </script>
  
<div class="p-8">
    <Table bordered>
        <thead>
          <tr>
            <th>#</th>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Username</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row">1</th>
            <td>Mark</td>
            <td>Otto</td>
            <td>@mdo</td>
          </tr>
          <tr>
            <th scope="row">2</th>
            <td>Jacob</td>
            <td>Thornton</td>
            <td>@fat</td>
          </tr>
          <tr>
            <th scope="row">3</th>
            <td>Larry</td>
            <td>the Bird</td>
            <td>@twitter</td>
          </tr>
        </tbody>
      </Table>
</div>