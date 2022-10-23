<template>
  <div>
    <LandingPageHero></LandingPageHero>
    <section
      v-for="(section, index) in sections"
      :key="section.header"
      class="section"
      :class="{ 'section--alternate': index % 2 === 0 }"
    >
      <TextAndImage class="u-max-page-width" :data="section" :is-alternate="index % 2 === 0" />
    </section>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      sections: [
        {
          header: 'Reiki',
          text: [
            'Reiki wurde als Heilkunde und spiritueller Weg im frühen 20. Jahrhundert von Mikao Usui begründet. Hierbei werden die Hände auf den Körper gelegt, um die unsichtbare Lebensenergie zu teilen, die jeden und alles durchströmt.',
            'Der Körper verfügt über eine angeborene Intelligenz, die Zugang zu einer heilen Version von uns besitzt, Reiki kann unterstützend wirken mit dieser Heilkraft in Verbindung zu treten um Harmonie, Ganzheit und Heilung in unser Leben fließen zu lassen.',
          ],
          image: {
            altText: 'TODO',
            path: '/images/jay-castor-7AcMUSYRZpU-unsplash.jpg',
          },
        },
        {
          header: 'Meditation',
          text: [
            '... ein ruhiger Geist hört, was die Seele flüstert...',
            'Meditation ist ein wirkungsvolles Heilmittel, um die Ordnung und Kohärenz unseres physischen und psychischen Körpers wieder herzustellen.',
            'Die wissenschaftlich belegten positiven Eigenschaften Sund unter anderem : Stärkung des Immunsystems, Senkung des Stresspegels, Lösung von Muskelverspannungen, Senkung des Blutdrucks.',
            'Wir können lernen, die Stimme unseres Herzens wieder wahrzunehmen und ihr zu folgen.',
          ],
          image: {
            altText: 'TODO',
            path: '/images/sabine-schulte-Dj8reMyS-Z4-unsplash.jpg',
          },
        },
        {
          header: 'Chakren',
          text: [
            'Chakren sind wichtige Energiezentren im Körper. Sie beeinflussen unsere physische, psychische und seelische Gesundheit.',
            'Meditation und Reiki kann helfen, die Chagrin wieder in Einklang und Harmonie zu bringen, was wiederum positive Auswirkungen auf das Energiefeld des Körpers und dem allgemeinen Wohlbefinden hat.',
          ],
          image: {
            altText: 'TODO',
            path: '/images/rodolfo-sanches-carvalho-9W-OGQjQwlk-unsplash.jpg',
          },
        },
        {
          header: 'Sabrina Dussin',
          text: [
            'Mein Name ist Sabrina Dussin. Ich bin 40 Jahre alt, verheiratet und Mutter von drei Kindern.',
            'Seit meiner Kindheit war mir bewusst, dass es da noch mehr gibt zwischen Himmel und Erde und den Dingen, die wir mit unseren Augen sehen können. Ich konnte es aber nicht genau benennen oder zuordnen und schon garnicht im Detail mit anderen besprechen.',
            'In den letzten Jahren hatte ich verschiedene Begegnungen, Gespräche und Erlebnisse, die mein Gefühl „Da ist noch etwas Anderes“ gestärkt haben und mich voller Überzeugung zum Reiki geführt haben. So habe ich die spirituellen Weisheiten, Gedanken, sowie psychologisch wissenschaftlichen Ansichten mehr und mehr in mein Leben integriert.',
            'Ich freue mich meine Erfahrungen weiterzugeben und die Energien fließen zu lassen. Falls Du Dich angesprochen fühlst und Interesse hast, melde Dich herzlich gerne telefonisch oder per Email bei mir.',
            'Ich freue mich darauf, Dich kennenzulernen.',
          ],
          image: {
            altText: 'Portrait von Sabrina Dussin',
            path: '/images/portrait-sabrina.jpg',
          },
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@use '/assets/styles/variables';

.section {
  padding: variables.$space-xl 0;
  &--alternate {
    background-color: variables.$background-color-alternate;
  }
}
</style>
