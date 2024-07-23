
import { format, parse } from 'date-fns'

const TimeFormat = 'HH:mm:ss'

function utcToLocalTime(utcTime: string | undefined): string | undefined {
    if (!utcTime) return undefined
    const date = parse(utcTime, TimeFormat, new Date())

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
      TimeFormat
    )
  }


  function localTimeToUtc(localTime: string | undefined): string | undefined {
    if (!localTime) return undefined
    const date = parse(localTime, TimeFormat, new Date())

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
      FULL_TIME_FORMAT
    )
  }