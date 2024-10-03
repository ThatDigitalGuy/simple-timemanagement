<script lang="ts">
  import {
    Button,
    Card,
    CardBody,
    CardHeader,
    CardTitle,
    Input,
    FormGroup,
  } from "@sveltestrap/sveltestrap";

  const handleSubmitLog = async () => {
    const dateForm = document.getElementById("formDate");
    const timeFromForm = document.getElementById("formTimeFrom");
    const timeToForm = document.getElementById("formTimeDone");
    const whereForm = document.getElementById("whereForm");

    const payload = JSON.stringify({
      "date": dateForm?.value,
      "from": timeFromForm?.value,
      "to": timeToForm?.value,
      "where": whereForm?.value,
    });

    console.log(payload)

    const request = await fetch('https://db.rhysmason.uk/api/v2/tables/mmajcep1y0ye0jm/records', {
      method: "POST",
      headers: {
        "content-type": "application/json",
        'xc-token': "Q8YZuXP7WkAUPFE9-ZnpQ_AAXQ-8JdLPeFAitgDI"
      },
      body: payload
    });
  };
</script>

<Card>
  <CardHeader>
    <CardTitle>Log Hours</CardTitle>
  </CardHeader>
  <CardBody>
    <div class="p-4">
      <div class="mb-2">
        <FormGroup floating label="Date?">
          <Input id="formDate" type="date" placeholder="date placeholder" />
        </FormGroup>
      </div>
      <div class="mb-2">
        <FormGroup floating label="When did you start?">
          <Input id="formTimeFrom" type="time" placeholder="date placeholder" />
        </FormGroup>
      </div>
      <div class="mb-2">
        <FormGroup floating label="When did you finish?">
          <Input id="formTimeDone" type="time" placeholder="date placeholder" />
        </FormGroup>
      </div>
      <div class="mb-2">
        <FormGroup floating label="Where?">
          <Input id="whereForm" placeholder="Where?" />
        </FormGroup>
      </div>
    </div>
    <Button on:click={handleSubmitLog}>Submit</Button>
  </CardBody>
</Card>
