<script lang="ts">
  import { data } from './data.example.js'
  import { DataHandler, Datatable, Th, ThFilter } from '@vincjo/datatables'

  const handler = new DataHandler(data, { rowsPerPage: 10 })
  const rows = handler.getRows()

</script>

<Datatable {handler}>
  <table>
      <thead>
          <tr>
              <th>No</th>
              <th>Noti</th>
              <th>Part</th>
              <Th {handler} orderBy="receipt_no">Recipt No</Th>
              <Th {handler} orderBy="request_comment">Request Comment</Th>
              <Th {handler} orderBy="status">Status</Th>
              <Th {handler} orderBy="promise_dt">Promise Dt</Th>
              <Th {handler} orderBy="product">Product</Th>
              <Th {handler} orderBy="model">Model</Th>
              <Th {handler} orderBy="serial_no">Serial No</Th>
              <Th {handler} orderBy="symptom">symptom</Th>
          </tr>
          <!-- <tr>
              <th/>
              <th/>
              <th/>
              <ThFilter {handler} filterBy="receipt_no"/>
              <ThFilter {handler} filterBy="request_comment"/>
              <ThFilter {handler} filterBy="status"/>
              <ThFilter {handler} filterBy="promise_dt"/>
              <ThFilter {handler} filterBy="product"/>
              <ThFilter {handler} filterBy="model"/>
              <ThFilter {handler} filterBy="serial_no"/>
              <ThFilter {handler} filterBy="symptom"/>
          </tr> -->
      </thead>
      <tbody>
          {#each $rows as row}
              <tr>
                <td>{row.id}</td>
                <td><input type="checkbox"></td>
                <td><input type="checkbox"></td>
                  <td>{row.receipt_no}</td>
                  <td>{row.request_comment}</td>
                  <td>{row.status}</td>
                  <td>{row.promise_dt}</td>
                  <td>{row.product}</td>
                  <td>{row.model}</td>
                  <td>{row.serial_no}</td>
                  <td>{row.symptom}</td>
              </tr>
          {/each}
      </tbody>
  </table>
</Datatable>

<style>
  thead {
      background: #fff;
  }
  tbody td {
      border: 1px solid #f5f5f5;
      padding: 4px 20px;
  }
  tbody tr {
      transition: all, 0.2s;
  }
  tbody tr:hover {
      background: #f5f5f5;
  }
</style>