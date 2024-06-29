+++
draft = true
date = 2024-06-14
title = "Highly-scalable brittle systems are not resilient"
description = "A robust monolith may serve you better than a highly scalable fragile system"
slug = "risk-and-scalability"
authors = ["Diogo Pessoa"]
tags = ["System Design", "Risk", "Reflections"]
categories = ["system-design", "reflections"]

+++

{{<toc>}}

## Summary

My experience in assessing risk in distributed systems and the scary reality of the
building brittle microservices.



## Fragility and robustness

## risk exposure assessment

If you're running a single node, forget about log rotation or shiny alerts, they're just
noise.

This scenario is simple benefit 0, risk exposure 100%. The process crashes you're done.

Same goes for a multi-replica setup. If you're relying on a single Database, you're
done. `(Ahh but what do you take me for. I'm replicating my DB.)`. Great, how's your
network setup. Ah, we're multi-AZ, :clap:. Single VPC? single gateway? How deep and
unconformable are you willing to go?

The challenge in risk assessment, is not finding the SPoF (Single-point of failure).
It's confronting the discomfort, the feeling of exposure, vulnerability.

### How conformable are you with discomfort?

`(Oh yeah, this is philosophical, the tech stuff is just an excuse.)`

If as an individual you're not using to that feeling of panic. That feeling you have
when you thought you left the oven on, and you're 2 hours away from home. That's how
you'll feel when you are confronting your own system-design
flaws. `(and yes, we all done it before. It's like picking your nose when driving. The traffic light is red, and you're alone in the car...)`
If anybody asks you'll deny it, even if as a reflex, you'll say no I don't do that.

My point is, before you are ready to build a really robust system, you'll have to be
conformable with the discomfort. I learned to laugh at my own mistakes, and even being
the first in the room to talk about it. It disarms others, it also gets you head in the
right spot.

## Cool, we're now super cool-headed (monk level shit), back to System design.

Just before we start another thought to consider:

**_"If a factory is torn down but the rationality which produced it is left standing,
then that rationality will simply produce another factory. If a revolution destroys a
government, but the systematic patterns of thought that produced that government are
left intact, then those patterns will repeat themselves. . . . There’s so much talk
about the system. And so little understanding."_** – Robert Pirsig. 

—ROBERT PIRSIG, Zen and the Art of Motorcycle Maintenance

### High Scalable, but is it?

### SLAs, SLOs, monitoring, Alerts and the technical contorts a brittle system requires

### You know what's better than an super response team? Not having an outage

### Pick your metrics right! no, not that metric. Be wise in how you measure the success of your team output

## Conclusion

Standing in the shoulder of giants `(Ironically, also a quote)`: *
*_"everything fails all the time"_** – Werner
Vogels, Amazon's CTO.

This reflection is not on better Observability, scalability or run-books. It's about
design, think about your work, respect your system for what it is a dynamic complex
ecosystem, bound to fail. `(That's sounded pretty poetic)` :performing_arts:

Design for failure, build a robust mindset. Then, extend that to the work output. Work
on a robust system, it might take an extra sprint or two, but keep in mind the end of a
sprint is an imaginary end line. It's a social convention, a common accord among
rational
engineers. If it gets in the way of quality,
adjust!
It's fine, really. The Power pointers out there will be sad. But your users will be
happier, because of your backbone. They'll never thank you or even know it. But, if you
want recognition, go be a Power pointer.

It all goes back to how you measure your success. I'm happy with a good day's work
and `quality` output. The rest is bullshit.

## References

1. [Nicholas Nassim Taleb, Anti fragile](https://en.wikipedia.org/wiki/Antifragile)
2. [Normal Accidents](https://en.wikipedia.org/wiki/Normal_Accidents)
3. [Thinking in Systems](https://donellameadows.org/systems-thinking-book-sale/)
4. [Zen and the Art of Motorcycle Maintenance](https://en.wikipedia.org/wiki/Zen_and_the_Art_of_Motorcycle_Maintenance)
