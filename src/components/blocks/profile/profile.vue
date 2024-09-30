<script setup>

// IMPORTS
import './profile.scss';
import Heading from '@/components/partials/heading/heading.vue';
import Paragraph from '@/components/partials/paragraph/paragraph.vue';
import Link from '@/components/partials/link/link.vue';
import { onMounted, ref } from 'vue';

// DEFINE ELEMENTS AND COUNTER
const counter = ref(0);
let elements;

// HELPER FUNCTION TO CREATE A DELAY USING A PROMISE
const delay = (ms) => new Promise(resolve => setTimeout(resolve, ms));

// ON FIRST RENDER
onMounted(() => {

  // GET ALL HIGHLIGHTED TEXT
  elements = document.querySelectorAll('.profile__highlight');

  // START LOOP
  setTimeout(() => {
    highlightNextElement();
  }, 3000);

});

// INIT LOOP
const highlightNextElement = async () => {

  // GET THE CURRENT ELEMENT AND ADD THE 'ACTIVE' CLASS
  const currentElement = elements[counter.value];
  currentElement.classList.add('highlight--active');

  // WAIT FOR 3 SECONDS WHILE THE ELEMENT IS HIGHLIGHTED
  setTimeout(() => {

    // REMOVE THE 'ACTIVE' CLASS AFTER 3 SECONDS
    currentElement.classList.remove('highlight--active');

    // WAIT FOR ANOTHER 1.5 SECONDS BEFORE MOVING TO THE NEXT ELEMENT
    setTimeout(() => {

      // MOVE TO THE NEXT ELEMENT, LOOPING BACK TO THE START IF NECESSARY
      counter.value = (counter.value + 1) % elements.length;

      // RECURSIVELY CALL THE FUNCTION TO CONTINUE THE LOOP
      highlightNextElement();

    }, 1500);

  }, 3000);

};

</script>

<template>
  <div class="profile">
    <Heading className="profile__heading" level="h1">Grüezi!</Heading>
    <div class="profile__avatar avatar">
      <img class="avatar__image" src="/images/jeromehaas.png" alt="Jérôme Haas">
    </div>
    <Paragraph className="profile__text">Mein Name ist <span class="profile__highlight">Jérôme Haas</span>, ich bin <span class="profile__highlight">31 Jahre</span> alt und arbeite als <span class="profile__highlight">Frontend-Engineer</span> in Zürich. Neben meiner beruflichen Tätigkeit absolviere ich ein <span class="profile__highlight">Teilzeit-Studium in Informatik</span>, um mein Wissen und meine Fähigkeiten in diesem Bereich weiter zu vertiefen.</Paragraph>
    <Paragraph className="profile__text">In meiner Freizeit beschäftige ich mich gerne mit privaten <span class="profile__highlight">Software-Projekten</span>, <span class="profile__highlight">Kochen</span> und dem <span class="profile__highlight">Laufsport</span>. Diese Aktivitäten bieten mir einen wertvollen Ausgleich zu meinem beruflichen Alltag. Ich bin eine <span class="profile__highlight">ruhige, zuverlässige und verantwortungsbewusste Person</span>, die großen Wert auf ein gepflegtes und harmonisches Wohnumfeld legt. Ich bin <span class="profile__highlight"> Nicht-Raucher</span>, ledig, spiele <span class="profile__highlight">kein Musikinstrument </span> und habe <span class="profile__highlight">keine Haustiere</span>.</Paragraph>
    <Paragraph className="profile__text">Mein aktuelles <span class="profile__highlight">Jahresgehalt beträgt CHF 91'000</span>. Davon verdiene ich CHF 76'000 als Frontend-Engineer bei der goTom AG (80% Pensum) und CHF 15'000 kommen durchschnittlich aus passivem Einkommen privater Softwareprojekte hinzu. Ab dem Sommer 2027 plane ich mein Pensum auf 100% zu erhöhen, was mein jährliches Einkommen vorraussichtlich auf CHF 115’000 steigen lassen wird.</Paragraph>
    <Paragraph className="profile__text">Da ich mich zurzeit <span class="profile__highlight">uf der Suche nach einer langfristigen und passenden Wohnmöglichkeit befinde</span>, würde ich mich sehr freuen, wenn Sie mir die Gelegenheit geben würden, mich persönlich vorzustellen und meine Bewerbungs-Unterlagen näher zu erläutern.</Paragraph>
    <div class="profile__infos infos">
      <div class="infos__block block">
        <Heading className="block__heading" level="h2">Adresse</Heading>
        <Paragraph className="block__text">Bodenmatte 16a</Paragraph>
        <Paragraph className="block__text">5647 Oberrüti</Paragraph>
        <Paragraph className="block__text">Schweiz</Paragraph>
      </div>
      <div class="infos__block block">
        <Heading className="block__heading" level="h2">Kontakt</Heading>
        <Paragraph className="block__text">E-Mail:
          <Link className="block__link link" href="mailto:hello@jeromehaas.ch">hello@jeromehaas.ch</Link>
        </Paragraph>
        <Paragraph className="block__text">Mobile:
          <Link className="block__link link" href="tel:0795129016">079 512 90 16</Link>
        </Paragraph>
      </div>
      <div class="infos__block block">
        <Heading className="block__heading" level="h2">Links</Heading>
        <Paragraph className="block__text">
          <Link className="block__link link--with-icon" href="/documents/bewerbungsformular.pdf">Bewerbungsformular</Link>
        </Paragraph>
        <Paragraph className="block__text">
          <Link className="block__link link--with-icon" href="/documents/strafregister-auszug.pdf">Strafregister-Auszug</Link>
        </Paragraph>
        <Paragraph className="block__text">
          <Link className="block__link link--with-icon" href="/documents/betreibungsregister-auszug.pdf">Betreibungsregister-Auszug</Link>
        </Paragraph>
      </div>
    </div>
    <hr class="profile__separator">
    <div class="profile__references references">
      <Heading className="references__heading" level="h2">Referenzen</Heading>
      <div class="references__block block">
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/calendar.svg"/>
          <Paragraph className="item__text">01.05.2020 - heute</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/location.svg"/>
          <Paragraph className="item__text">Bodenmatte 16a, 5647 Oberrüti</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/avatar.svg"/>
          <Paragraph className="item__text">Johannes Lehner</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/phone.svg"/>
          <Link className="item__link" href="tel:+41787788842">
            <Paragraph className="item__text">+41 78 778 88 42</Paragraph>
          </Link>
        </div>
      </div>
      <div class="references__block block">
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/calendar.svg"/>
          <Paragraph className="item__text">01.12.2017 - 01.05.2020</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/location.svg"/>
          <Paragraph className="item__text">Reckenbühlstrasse 14, 6005 Luzern</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/avatar.svg"/>
          <Paragraph className="item__text">Susanne Stahl</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/phone.svg"/>
          <Link className="item__link" href="tel:+41765889192">
            <Paragraph className="item__text">+41 76 588 91 92</Paragraph>
          </Link>
        </div>
      </div>
    </div>
    <hr class="profile__separator">
    <div class="profile__employer employer">
      <Heading className="employer__heading" level="h2">Arbeitgeber</Heading>
      <div class="employer__block block">
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/calendar.svg"/>
          <Paragraph className="item__text">goTom AG</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/location.svg"/>
          <Paragraph className="item__text">Lessingstrasse 11, 8002 Zürich</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/web.svg"/>
          <Link className="item__link" href="https://www.gotom.io">
            <Paragraph className="item__text">www.gotom.io</Paragraph>
          </Link>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/avatar.svg"/>
          <Paragraph className="item__text">Michaela Lindegger</Paragraph>
        </div>
        <div class="block__item item">
          <img class="item__icon" src="@/assets/icons/phone.svg"/>
          <Paragraph className="item__text">auf Anfrage</Paragraph>
        </div>
      </div>
    </div>
  </div>
</template>