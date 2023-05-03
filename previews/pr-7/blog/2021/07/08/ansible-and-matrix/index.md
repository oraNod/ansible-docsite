---
title: Ansible and Matrix
author: Greg Sutcliffe
date: 2021-07-08 13:00:00 UTC
slug: ansible-and-matrix
category: community-team
tags: matrix, irc, strategy, community
type: text
---

# Building bridges - where the Ansible community needs to go next with chat

This post is long, because I have a lot to cover. But I'm going to lead with
the big picture, and if you want details, you can keep reading. Please note
that at this stage, this represents *my* views - as I will repeat at the end,
my goal is to have the community ratify this, but first I have to convince you
:)

The world turns, and we move with it. The way in which we communicate has
evolved, as it always has, and periodically we must catch up if we want to
attract new people to our community. Today, that means offering a place where
new and existing contributors feel welcomed, safe, and valued, with a rich
interface and a low barrier to entry. I want to help build that, because I fear
that if we don't, we will fade, and Ansible deserves better than that.

I'm going to lay out how to use the solid base of IRC to become a Matrix-first
(but not only, **IRC will remain**) community, and how I hope to move things
forward from the Red Hat side. I know this can be a hot topic for some folks,
so (a) please keep the discussion civil, and (b) I *want* to hear those
concerns so that we get this right. That said, "right" has to be for the
*whole* community.

# Future Vision - where I'd like to get to in the next 6 months

I'm going to go into the specifics of Matrix & IRC later on, but let me start
with [this quote from Thibault Martin over at
GNOME](https://discourse.gnome.org/t/irc-matrix-and-thanks-for-all-the-kicks/6482):

> IRC used to be the top notch system for a while, and is still pretty
> reliable. There are issues here and there, but given how basic the whole
> protocol is, it is fairly sturdy. The frugality of the protocol that was once
> its strength has turned into its weakness in the modern world. **People’s
> expectations have shifted**. Most of our contributing community is already
> “working for the computer” when producing the great software we all enjoy.
> It’s time for instant messaging to get out of the way, and to allow the
> computer to work for us when it comes to talking to each other. No NickServ
> spells, no ChanServ incantations, no bouncer to rent or to host on a server.
> **It’s time for us to just enter our credentials, browse the channels, and
> enjoy the conversation with the ones we like to work with.**

**I *was* a long time IRC user, it *was* the right choice a decade ago; it is
not today**, and so I agree with Thibault. For our community to grow, we must
attract new contributors, and they will want to talk with us. Whilst IRC was
once the go-to for that, it no longer is. However, it's not sufficient to ask
*ourselves* what we like, that would be [survivor
bias](https://en.wikipedia.org/wiki/Survivorship_bias). By asking the people
who are already happy with IRC if we should keep it, we'll ignore the folks who
didn't join because they struggled with IRC. We want to account for those
people - we don't know who they are, of course, so we must intuit how to make
their life easier. This is why I've spent the last month talking with
communities such as GNOME,
[KDE](https://dot.kde.org/2019/02/20/kde-adding-matrix-its-im-framework),
[Mozilla](http://exple.tive.org/blarg/2019/12/19/over-the-line/),
[Fedora](https://discussion.fedoraproject.org/t/the-future-of-real-time-chat-discussion-for-the-fedora-council/24628/27),
and
[OpenDev](https://review.opendev.org/c/zuul/zuul/+/793669/1/doc/source/reference/developer/specs/community-matrix.rst)
about their plans and experiences with this.

I know many of you love IRC, and others are specifically wary of Matrix. I'll
address that shortly. But to round out this section, I'll give you *my* view of
where the community needs to be in a moderate amount of time (3-6 months):

- Matrix becomes the default for new users
    - We (the community) promote it actively, that is:
        - We encourage the use of its richness (emoji reactions, posting images etc.)
        - We add it to our docs as the way to enagage with us
        - We make a clear statement that we are a Matrix-first community
    - We (Red Hat) contribute through paying for Element Hosting, being good FOSS citizens and supporting our supply chain
        - This means Matrix rooms can get addresses like `#welcome:ansible.com`
        - We can potentially give out Matrix accounts to contributors (more on that later)
- IRC is maintained
    - **IRC does not go away!** Users who are comfortable with their workflow should not be abandoned
        - Users who express an interest in making their setup work in Matrix should be helped to do so
        - Concerns should be addressed where possible. There are a *lot* of tuning options we can use to improve the IRC-side experience, but we need to bear in mind that the goal *is* to modernise our chat, and some change comes along with that.
    - We aim for a gradual osmosis of users to Matrix, aided by giving out Ansible Matrix accounts where suitable
- We work on making more use of Matrix
    - Use/write Matrix bots rather than IRC ones (there's a GitHub bot already for example, and an RSS bot)
    - Running conferences on Matrix instead of GMeet / Bluejeans (I have a PoC for this)
    - Richer tooling for running online meetings (linkable chat, embedded etherpads, etc)
    - (There's many more things we could try, but for brevity I'll stop here)

I'm excited. I know from my work as a community lead for Satellite/TheForeman
that tiny features like being able to give a "thumbs-up" or a "heart" emoji on
a comment from a colleague might seem trivial, but it means *the world* for
building the [social glue](https://noidea.dog/glue) that so often is lacking in
online interactions. It's just one example of where richer interaction
(combined with a lower barrier to entry, as Thibault said) will reap us rewards
as a community.

The idea that a future Contributor Summit would be *right there* in the
Community room for all to view the stream and participate makes me very happy -
having it in a silo in GMeet means we get far lower participation. KDE are
doing that right now for Akademy (using BigBlueButton), and of course the
entire of FOSDEM 2021 was on Matrix/Jitsi, so it's possible.

The possibilities for bots and widgets are likewise huge - Matrix has a REST
API for writing bots (and an SDK), and Element can embed HTML widgets in the UI
(e.g. KDE are working on a Q&A poll app for doing talks). If we make the rooms
fully public (rather than just open to anyone to join) then you can get an URL
for any line in the chat history, which would mean forgetting to start Zodbot
isn't so critical (although it still has features we like, ofc). There's so
much more we could do here, especially in collaboration with other communities.
In particular I'd like to experiment with the GitHub Matrix bot that already
exists, but there's also Etherpads, Calendars, room conferencing, RSS, Travis
bots, and we can always write our own.

# Justifying Matrix as the choice

Before we talk about Matrix in more detail, I think it's helpful to review the
issues I see with IRC. I want to stress again that IRC is *not* going away. It
works for many, and I don't dispute that. But I'll refer back to that [survivor
bias](https://en.wikipedia.org/wiki/Survivorship_bias#/media/File:Survivorship-bias.svg)
- I no longer believe it works for *new* contributors joining us today.

## What's wrong with IRC?

If you ask Mozilla that question, ["everything" is the
answer](http://exple.tive.org/blarg/2019/04/26/synchronous-text/), but I don't
agree 100%. Some of those concerns apply to us, some do not. In particular,
Mike Hoye talks about the problems with unauthenticated networks and
spam/hostile chat - we can use channel modes on Libera that require
registration. However, the rest of his points stand:
- Available interfaces haven't kept up with modern expectations
- Spam / harassement is endemic to the platform (not in our channels, but if
  our users are in other channels they will be exposed to it)
- IRC is frequently blocked from within institutions & corporate networks
  (often because of the IRC spam in general, even if it doesn't affect us)
- The Freenode drama has shown that there's also an issue of organisational
  ownership. We lost everything on Freenode because of the drama of others.

However, whether that adds up to "IRC is bad" depends on your use case:

### I already use IRC, why should I stop?

As I said, I think for existing IRC users it's fine. You don't need to stop if
you're happy. You've already got your spam protection in place, you've already
cast the Nickserv spells, and your organisations clearly permit IRC traffic.
Carry on! But take a second, and read over that list of things again. How easy
is it for someone unfamiliar with the world of IRC to do that?

### I'm new, should I use IRC?

No. It's not what people expect of a modern chat system - Nickserv is ...
unintuitive (to be polite) compared to signup systems people encounter today,
access is hard (and frequently blocked at network level), the rich interface
isn't there, and there's no persistence (without a bouncer, which can be even
harder to get right than Nickserv). It's an **unnecessarily huge** barrier to
entry, to a platform that **doesn't meet expectations of new users anyway**.
That's an *enormous* ask for people who aren't deeply embedded in the project.
I find it unsurprising that IRC growth in general has been outpaced by other
platforms, and we are no exception.

### I'm an organisation, should I set up on IRC?

If I was setting up a new project *today*, no, I would not use IRC. For an
organisation, three things come up. Firstly, access & recruitment - as we've
discussed already, a FOSS project needs volunteers, and when we put big
barriers in the way, we wither. Secondly, keeping members safe - we have a CoC,
but with the way IRC works, it isn't easy to apply, and we cannot ask people to
agree to the CoC the way we do in other places. Third, ownership - the recent
Freenode drama demonstrated that we didn't have control of our own chat domain
that we *would* have in, say, a forum or by email, and instead watched helpless
as our community was fractured by the actions of others.

I don't think we're yet at the point of declaring IRC a "legacy" system (as
GNOME are
[considering](https://discourse.gnome.org/t/irc-matrix-and-thanks-for-all-the-kicks/6482)),
but I do think it's time to start our journey into something more modern and
welcoming to the newest of the community. That platform is Matrix - and I as
said in the section header, we need to justify that...

# What does Matrix bring us?

First we need to define what [Matrix](https://matrix.org) *is*, because I see
this getting conflated all the time. Matrix is a *protocol* for real-time
communication (be that text, audio, video or even file sharing). It is *not* a
client, any more than Thunderbird is SMTP or Hexchat is IRC. Concerns such as
"Matrix is bloated and slow" or "I like my IRSSI interface" need to be taken
aside, because that's a *client* discussion - a valid discussion for sure, but
not in scope here. Those interested may want to look at [the clients
page](https://matrix.org/clients), there are *many* options, from full web UI
to a plugin for WeeChat.

## Matrix for the old IRC user

I'm assuming here that this user *wants* to try a Matrix account - those who
wish to remain on IRC can do so. If so, well, little changes really. Matrix can
be used as IRC, you're just ignoring the richer features like image sharing
etc. (there's even an IRC display style in Element). Thanks to
[bridging](https://matrix.org/bridges) you can hop directly into IRC channels
on some IRC networks (Libera and OFTC to name two). You'll get persistence for
free (no need to run a bouncer), and you can continue largely as normal (this
has been my workflow for the last 4 years).

## Matrix for the new user

I've already spoken about new-user expectations, so you'd expect that Matrix is
similar compared to the likes of Slack etc. All the features you'd expect
(reactions, notifications, replies, etc.) are there. The get-started flow is
easy too - since [Element exists as a webapp](https://app.element.io), new
users can load it in a browser and try it out. If they wish to dive in, they
can grab a standalone desktop and/or mobile client for easier access. As such,
much of the barrier to entry is removed - no arcane Nickserv process
(registraion is either email-based or SSO, as you would expect of a modern
service), traffic is not blocked so often, and persistence is there by default.

In either case, it's worth reading this comparison of [Matrix vs
Email](https://blog.ergaster.org/post/20210602-matrix-for-im/) as many of the
concepts of email carry over.

## Matrix for the organisation

OK, this is the big one - what does Matrix mean for *the Ansible community* as
a whole? I'm going to spend a bit more time on this one, because we're all
familiar with chatting, but perhaps these organisational points are a bit more
nuanced.

### Access and recruitment

As we've said, Matrix supports the feature set that users have come to expect
from modern chat. It's no surprise that Ansible would like to grow its
community of contributors, but it goes deeper. With the incoming
"[Spaces](https://matrix.org/blog/2021/05/17/the-matrix-space-beta/)" feature,
Matrix allows us to bring together rooms into a logical hierarchy, and link to
the whole space with a single URL. That's an easy link to drop into our docs,
into our chats, and into our blogs / social media, encouraging others to join
us. It's essentially bringing our [IRC docs
page](https://docs.ansible.com/ansible/latest/community/communication.html#irc-channels)
into Matrix and making it one click to jump into a Working Group or similar.
With Suggested Rooms marked clearly, new members can find their way to good
places to ask questions.

(Note Spaces are still experimental and in beta - this is the intended goal,
but for now we would link to the Matrix rooms on the docs page).

Going further, we could make our rooms completely public, which allows
"peeking" in Matrix terms - that lets guests view the chat (in read-only mode)
before they sign up, allowing them a one-click, in-browser view to check if
this is indeed the right channel to join and ask their question - it's hard to
make the barrier lower than that. I have enabled this in [a small working group
room](https://matrix.to/#/#jboss-wg:ansible.im) if anyone wishes to try it.

### Safety and conduct

Matrix has good tooling for moderation and conduct. Unlike IRC, there's no such
thing as an unauthenticated Matrix user (there are guest users but that's not
the same thing, and are currently broken anyway), so spam is far less of a
problem (in fact I've only seen a single serious spam attack on Matrix, and it
was handled far better than IRC). If it's harassment rather than spam, then as
with any chat platform, it is possible to kick or permanently ban any problem
users, and it's much more intuitive than on IRC.

However, Matrix brings with it something of a quiet revolution in moderation.
Matrix is federated (which we haven't spent much time talking about yet) and
that means there are other people operating Matrix servers - and in (yet
another) analogy to email, we can share information about bad actors. Similarly
to how one can subscribe to blocklists for your own email server, Matrix
servers [can share information about
*banlists*](https://github.com/matrix-org/mjolnir/blob/main/docs/moderators.md#list-management).
This is *huge* - if we decide we trust another group (say, Fedora), then we can
subscribe to their banlists, and any bad actors there are immediately removed
from our community as well. Forming a group of projects that share values and
codes of conduct could make this very strong.

The tools for enforcing the standards we expect of our community run much
deeper, but I don't want to go on forever. I'll link to [this
piece](http://exple.tive.org/blarg/2019/12/19/over-the-line/) for some thoughts
from Mozilla on Matrix's tooling around CoC enforcement.

### Ownership

What does the name of a project mean? When a person emails from a work account,
what values do they represent? When you join the chat room of a group, who are
you talking to? Ownership, namespacing, domains, sovereignty, it has many
names, but it is critical.

The Freenode drama showed that we can lose that quickly if we're not careful;
almost overnight, all our rooms were empty, the namespace meaningless. The same
risk is true of Libera in fact - although I personally trust the admins of
Libera, it's still a 3rd-party network. Also true of Slack, Discord, etc. In
fact, only email really nails this (oh look, email again). I don't have an
Ansible email address, but I do have a Red Hat one, and only Red Hat can take
it away from me. When I email from that, I'm doing Red Hat stuff, and that
matters.

Matrix can do this too - in the same way that an email server uses an MX DNS
record, Matrix has namespaces. Our rooms can be `#devel:ansible.com` if we wish
them to be (a Matrix room can have many aliases), and the *primary* room
address confers powers to manage the room. So long as we hold the DNS, we also
hold the rooms - that's one of the benefits of federation.

It goes deeper though, because we'll have accounts to give out, on a second DNS
name (https://chat.ansible.im). Why a second domain? Well, here's some
[extensive
thoughts](https://blog.ergaster.org/post/20210610-sovereignty-federated-system-gnome)
on Matrix sovereignty, but one point made is about impersonation and
representation. These accounts will be available to the wider Ansible
community, and I don't want these accounts to be associated with Red Hat (i.e.
ansible.com) - they are for the *community* and ownership of an ansible.im MXID
should have the same gravitas as a project email address.

There are some decisions to be made about how to hand these accounts out (and
how we take them back, if need be) but I'll cover that later.

# How do we get there? a.k.a THE PLAN

OK, you have the vision, the concerns, the ways in which Matrix should improve
our situation. How do we get there though? There's a few things to do, some of
which are already in motion (because they're non-binding) and others need us to
collectively agree to implement them.

## Homeservers

My notes on sovereignty and domain ownership rest on having our own homeserver.
We could self-host this, however we aren't well set up for doing our own ops,
*and* we want to be supporting our FOSS supply chain. As such **we have secured
funding from Red Hat to pay for a Matrix homeserver with Element Hosting
(ems.element.io)**. This will give us the necessary domain ownership and user
accounts to get the community started on the transition to Matrix.

It's worth noting that *all* the communities I spoke to praise Element
*hugely*. Working with them has been a pleasure so far, and they are very open
to feedback, so I expect that relationship will go well and that we can make
improvements as we need to. Read the process that Mozilla [went
through](http://exple.tive.org/blarg/category/irc/) if you want to see how that
looked for them.

We are setting up *two* domains as noted earlier. The first is a small
admin-only instance for controlling the `ansible.com` namespace - giving us
Ansible primary room names and the moderation tools to enforce our CoC. The
accounts here will be for the folks maintaining the admin install (right now
myself & Gundalow, but we'll want to make the bus factor a bit lower in a short
time), and will not be for day-to-day use. The second is the main homeserver
for user accounts (`ansible.im`). These are both live as of 2021-06-24,
although the ansible.com instance is not yet federating while we work out
things with the DNS.

## User experience

I'm looking to https://chat.mozilla.org for inspiration here - clearly
displayed expectations of the user, links to the coduct pages, and so on. If
you make an account and log in, the conduct is shown again. Synapse (the
homeserver software) can store consent, so we can ask users to agree to the
Code of Conduct. The web UI is clear, we can link to it from our docs and
media, and people can hop into the Community channel as a first point of
contact. We're setting up ansible.im to look somewhat similar at the moment,
Gundalow is working on it (but we both suck at page design, so bear with us
:P).

The Matrix Foundation (who maintain the Libera bridge) have kindly granted us
admin on our Libera/Matrix rooms (by default `libera.chat` rooms have only the
bridge as admin), so once the `ansible.com` instance is working, I'll be able
to add the ":ansible.com" room ids to each room. I'm already starting to add
`:ansible.im` aliases as well, just for completeness. *No Libera.chat IRC
channels will change name* - these are aliases on the Matrix side only, and
we'll use names that make sense (e.g. `#community:ansible.com` will be an alias
to `#ansible-community:libera.chat`).

These rooms are already organised into a Space (`#ansible-space:matrix.org`
right now) and I'm meeting with Element in the coming weeks to give feedback on
Spaces in general, so let me know how you find that if you are in the Spaces
beta.

## Accounts

This is one area where we need to decide what to do. As we've discussed, a
Matrix account is akin to an email, and we don't just give out Ansible email
addresses to anyone. We should be similarly careful with Ansible accounts - we
would not want someone harassing others or running a scam with an Ansible ID.
This means we need two things - a system for handing out accounts, and a
protocol for taking them back.

To hand them out, I think it's clear that we don't want open registration.
Other groups (Mozilla, Fedora) do this, but they are larger and have other IAM
/ SSO systems to tie the Matrix IDs to - we do not. GNOME are in a similar
position, and are working on a system to tie into Keycloak that allows for
existing users to "vouch" for new requests, 2 vouchs gets an approval. That
system is not ready yet but GNOME are making it public and will welcome
collaboration. In the meantime, I suggest we have a manual-vouch, whereby an
admin (likely me, but not *only* me) receives a request and the request gets
the needed vouches from the community and then the account is created. Exact
details of making and handling requests are to be determined (by pull request
or similar?) but the principle is clear.

To remove an account is trivial technically, but we need a policy. Clearly, any
breach of our Code of Conduct is grounds for account removal - the safety of
our community is important. It would be natural to assume people who have
drifted away from Ansible should have their accounts reclaimed - but as we are
billed monthly per *active* user, this may not in practice be required (only if
the user is still active on Matrix, but not in Ansible, would this be needed).
We should reserve the right to do so though, even if in practice we don't use
it often. Once again, Thib has some
[thoughts](https://blog.ergaster.org/post/20210622-owning-your-matrix-account/)
which I agree with:

> If you break policy, **the organisation can and probably will take the
> account back** and leave you without a chance to retrieve your data. If you
> leave the organisation, the account can and should probably be taken back
> from you too. Those accounts can really be compared to work e-mail accounts:
> you should limit your activities with this account to what you do for the
> organisation who provides it, and can’t expect to keep it after you leave.

Sadly, the lack of multi-account clients does tend to push people towards using
a single Matrix account for everything, but in an ideal world that wouldn't be
true, and users would segregate their activies just as they do between work and
private email. For now though, it'll be painful, so while we *need* to have the
right to take back an account, I wouldn't *want* to use that right unless we
had to (either for violations or for cost reasons).

Importantly, Matrix is federated. No one is *required* to have an `ansible.im`
MXID to participate in our community. However, these accounts are part of the
package we bought, so we may as well use them, and they may be a useful perk or
good for users that haven't already gotten a Matrix ID.

One day, I'd love to have open registration for our community - but until we
have something to tie it to (such as Fedora and Mozilla do) then I think the
concerns above outweigh the benefits. We'll get there :)

## Interaction with IRC

Again I will reinforce that we have no plans to stop using IRC. Inevitably
though, some of the richness of a more modern system will be lost on IRC, and
we're going to have to take that on the chin. That said, much will work -
embedded etherpads can have a direct link for use outside of Matrix, likewise
Jitsi (or other conference call software like BBB) has an external URL. These
will always be clearly posted so that IRC users are not left out. Likewise
we're open to tuning the behaviour of the bridge in our rooms regarding edits
and long lines if that becomes a significant issue, and so on. In short, I do
not want IRC users feeling ignored - we should discuss issues as they arise.

# Let's roll

This is a step change for us, but a needed one (in my opinion). As a community,
I think we need to ratify two things:

1. That we, the Ansible community, accept Matrix as an equal partner to IRC, and we welcome full use of its feature set.
2. What our policy for giving and removing ansible.im accounts is.

I think I've covered (1) in my arguments earlier. For (2), my suggestions are
as above - a pull-request-based vouching workflow, needing 2 ACKs from existing
ansible.im accounts to grant access. For removal, we need some wording here but
I would suggest it's a power that only the steering commitee can excercise, and
that it's for either CoC violations or inactivity *within the Ansible
community*. I look forward to bringing both these statements to the steering
committee for ratifying in the near future.

Beyond that, I also want to see us do regular retrospectives so we can adjust
as we go. This is not a once-and-done thing, it's a long project, and we need
to listen if it's going to work. I think the first one would be ~1 month after
we start officially promoting Matrix.

I'm excited. I hope you are too.  Please feel reach to reach me for chat any
time (at `@gwmngilfen:ansible.im`) if you have questions. Thanks for reading to
the end :)

