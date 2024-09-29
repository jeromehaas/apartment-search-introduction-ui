<script setup>

// IMPORTS
import './metadata.scss';
import Heading from '@/components/partials/heading/heading.vue';
import Paragraph from '@/components/partials/paragraph/paragraph.vue';
import Link from '@/components/partials/link/link.vue';
</script>

<template>
  <div class="metadata">
    <div class="metadata__avatar avatar">
      <img class="avatar__image" src="/images/jeromehaas.png" alt="Jérôme Haas">
      <div class="avatar__background"></div>
    </div>
    <div class="metadata__personalities personalities">
      <Heading className="personalities__heading" level="h2">Jérôme Haas</Heading>
      <Paragraph className="personalities__text">Job: Frontend-Engineer</Paragraph>
      <Paragraph className="personalities__text">Geburtsdatum: 20.09.1993</Paragraph>
      <Paragraph className="personalities__text">Familienstand: ledig</Paragraph>
    </div>
    <div class="metadata__address address">
      <Heading className="address__heading" level="h2">Adresse</Heading>
      <Paragraph className="address__text">Bodenmatte 16a</Paragraph>
      <Paragraph className="address__text">5647 Oberrüti</Paragraph>
      <Paragraph className="address__text">Schweiz</Paragraph>
    </div>
    <div class="metadata__contact contact">
      <Heading className="contact__heading" level="h2">Kontakt</Heading>
      <Paragraph className="contact__text">E-Mail:
        <Link>hello@jeromehaas.ch</Link>
      </Paragraph>
      <Paragraph className="contact__text">Mobile:
        <Link>+41 79 512 90 16</Link>
      </Paragraph>
    </div>
    <div class="metadata__links links">
      <Heading className="links__heading" level="h2">Links</Heading>
      <Link className="links__link link--with-icon" hryyef="/documents/bewerbungsformular.pdf">Bewerbungsformular</Link>
      <Link className="links__link link--with-icon" href="/documents/betreibungsregister-auszug.pdf">Betreibungsregister-Auszug</Link>
      <Link className="links__link link--with-icon" href="/documents/strafregister-auszug.pdf">Strafregister-Auszug</Link>
    </div>
  </div>
</template>