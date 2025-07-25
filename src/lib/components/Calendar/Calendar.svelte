<script lang="ts">
  import { getLocalTimeZone, today } from "@internationalized/date";
  import { Calendar } from "bits-ui";

  const isDateUnavailable: Calendar.RootProps["isDateUnavailable"] = (date) => {
    return date.day === 17 || date.day === 18;
  };

  let value = $state(today(getLocalTimeZone()));
</script>

<Calendar.Root
  class="card inline-block border border-surface-200-800 bg-surface-50-950 shadow-xl mt-6 p-4"
  {isDateUnavailable}
  weekdayFormat="short"
  fixedWeeks={true}
  type="single"
  bind:value
>
  {#snippet children({ months, weekdays })}
    <Calendar.Header class="flex items-center justify-between">
      <Calendar.PrevButton class="btn-icon preset-filled-primary-500">
        <span>&larr;</span>
      </Calendar.PrevButton>
      <Calendar.Heading class="text-lg font-bold" />
      <Calendar.NextButton class="btn-icon preset-filled-primary-500">
        <span>&rarr;</span>
      </Calendar.NextButton>
    </Calendar.Header>
    <div
      class="flex flex-col space-y-4 pt-4 sm:flex-row sm:space-x-4 sm:space-y-0"
    >
      {#each months as month, i (i)}
        <Calendar.Grid class="w-full border-collapse select-none space-y-1">
          <Calendar.GridHead>
            <Calendar.GridRow class="mb-1 flex w-full justify-between">
              {#each weekdays as day}
                <Calendar.HeadCell
                  class="text-surface-600-400 font-normal! w-10 rounded-md text-xs"
                >
                  <div>{day.slice(0, 2)}</div>
                </Calendar.HeadCell>
              {/each}
            </Calendar.GridRow>
          </Calendar.GridHead>
          <Calendar.GridBody>
            {#each month.weeks as weekDates}
              <Calendar.GridRow class="flex w-full">
                {#each weekDates as date}
                  <Calendar.Cell
                    {date}
                    month={month.value}
                    class="p-0! relative size-10 text-center text-sm"
                  >
                    <Calendar.Day
                      class="rounded hover:border-surface-200-800 data-selected:bg-foreground data-disabled:text-surface-600-400 data-selected:preset-filled data-unavailable:text-surface-600-400 data-disabled:pointer-events-none data-outside-month:pointer-events-none data-selected:font-medium data-unavailable:line-through group relative inline-flex size-10 items-center justify-center whitespace-nowrap border border-transparent bg-transparent p-0 text-sm font-normal"
                    >
                      <div
                        class="bg-foreground group-data-selected:bg-surface-50-950 group-data-today:block absolute top-[5px] hidden size-1 rounded-full"
                      ></div>
                      {date.day}
                    </Calendar.Day>
                  </Calendar.Cell>
                {/each}
              </Calendar.GridRow>
            {/each}
          </Calendar.GridBody>
        </Calendar.Grid>
      {/each}
    </div>
  {/snippet}
</Calendar.Root>
