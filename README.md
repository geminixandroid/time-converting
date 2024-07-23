time-converting
=
### Typesciprt functions to convert local time to UTC and vise versa using [date-fns](https://github.com/date-fns/date-fns)
```typescript
import { format, parse } from 'date-fns'

const TIME_FORMAT = 'HH:mm:ss'

function utcToLocalTime(utcTime: string): string {
    const date = parse(utcTime, TIME_FORMAT, new Date())

    return format(
      new Date(
        Date.UTC(
          date.getFullYear(),
          date.getMonth(),
          date.getDate(),
          date.getHours(),
          date.getMinutes(),
          date.getSeconds(),
          date.getMilliseconds()
        )
      ),
      TIME_FORMAT
    )
  }

  function localTimeToUtc(localTime: string): string {
    const date = parse(localTime, TIME_FORMAT, new Date())

    return format(
      new Date(
        date.getUTCFullYear(),
        date.getUTCMonth(),
        date.getUTCDate(),
        date.getUTCHours(),
        date.getUTCMinutes(),
        date.getUTCSeconds(),
        date.getUTCMilliseconds()
      ),
      TIME_FORMAT
    )
  }
  ```