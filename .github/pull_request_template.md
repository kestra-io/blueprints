## Blueprint

<!-- One blueprint per PR. Describe what it does in one or two sentences. -->

## Checklist

- [ ] I ran this flow on Kestra 2.0 and it calls the real system named in the title (no hard-coded or simulated results)
- [ ] Every `type:` exists on [kestra.io/plugins](https://kestra.io/plugins)
- [ ] The file is in `flows/`, its `id` matches the filename, and the `extend` block has all 9 fields from the README
- [ ] `tags` and `subTags` come from the README taxonomy, `demo` is `false`
- [ ] Secrets use `{{ secret('NAME') }}`, nothing is hard-coded
