Make `chronicle verify-raw` classify Wrangler diagnostics more carefully. Colour
codes are stripped before matching, so a missing object is still reported as
`missing_remote` when Wrangler colours words inside the message. A marker now
counts only as a whole phrase on a line that holds nothing but markers or is an
error line, so unrelated text that merely mentions `NoSuchKey` stays a
`fetch_error`. Neither case ever reported `verified`.
