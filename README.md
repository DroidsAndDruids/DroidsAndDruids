# Droids and Druids

Página oficial del podcast [droidsanddruids.com](droidsanddruids.com)


- [Jekyll](https://jekyllrb.com/)
- [Hyde](https://github.com/poole/hyde)
- Hosted in [Netlify](https://www.netlify.com/)
- [Página de administración](droidsanddruids.com/admin)

Local:

```sh
docker run --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll:4.0 jekyll serve
```