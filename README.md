# deathcount
An awful lot of Americans have died from COVID-19. This page is here to help visualize those numbers in terms that make sense to human beings.

## Trump's Circle of Death
Inspired by a [protest at Trump International Hotel in Washington DC](https://www.huffpost.com/entry/protest-body-bags-trump-dc-hotel_n_5ea3097ec5b669fd89240d36). Here are some things we know:
- one occupied body bag is six feet long.
- 880 six-foot body bags make a mile.
- 88,000 dead Americans would make a hundred-mile circle.

As I write this we are 10,000 short of that number; I expect it won't be more than a few days before we're there.

If you're wondering why the circle around Mar-A-Lago is smaller than the circle around Bedminster, the answer is:  the circle looks smaller because online maps display more meters per pixel the further south you go.  So the circle is the same size, but the map is showing more.  Yes, I could probably solve this by fiddling around with background-size, but then I'd have to answer questions about what was going on with the image resolution.

Shoutouts to <a href="https://www.mapdevelopers.com/draw-circle-tool.php">Map Developers</a> and <a href="https://wiki.openstreetmap.org/wiki/Zoom_levels">the OpenStreetMap wiki</a> for helping me understand some hard things about drawing a circle on a map.  Maps and map developers are both pretty cool, and I wish we'd met under better circumstances.

### How Long Until....

This could be the base of a second-by-second countdown clock

````// expects a parse-able string like "Nov 3, 2020" or "Nov 3, 2020 12:34:56"
howLong = when => {
  const dMs = new Date(when).getTime()-Date.now(), 
  dS = ~~(dMs / 1000),
  dM = ~~(dS / 60),
  dH = ~~(dM / 60),
  dD = ~~(dH / 24);
  return {
    days: dD,
    hours: dH % (dD * 24),
    minutes: dM % (dH * 60),
    seconds: dS % (dM * 60)
  };
};````
