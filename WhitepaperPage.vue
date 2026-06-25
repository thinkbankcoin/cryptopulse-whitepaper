<template>
  <div class="whitepaper-page">
    <!-- Hero Section -->
    <section class="wp-hero">
      <div class="wp-hero__inner">
        <h1 class="wp-hero__title">{{ $t('whitepaper.hero.title') }}</h1>
        <p class="wp-hero__subtitle">{{ $t('whitepaper.hero.subtitle') }}</p>
        <p class="wp-hero__tagline">{{ $t('whitepaper.hero.tagline') }}</p>
        <p class="wp-hero__vision">{{ $t('whitepaper.hero.vision') }}</p>
        <p class="wp-hero__version">{{ $t('whitepaper.hero.version') }}</p>
      </div>
    </section>

    <!-- Table of Contents -->
    <nav class="wp-toc">
      <div class="wp-container">
        <h2 class="wp-toc__title">{{ $t('whitepaper.toc.title') }}</h2>
        <ol class="wp-toc__list">
          <li v-for="item in tocItems" :key="item.id" class="wp-toc__item">
            <a :href="'#' + item.id" class="wp-toc__link" @click.prevent="scrollTo(item.id)">{{ item.label }}</a>
            <ul v-if="item.children" class="wp-toc__sublist">
              <li v-for="child in item.children" :key="child.id" class="wp-toc__subitem">
                <a :href="'#' + child.id" class="wp-toc__link" @click.prevent="scrollTo(child.id)">{{ child.label }}</a>
              </li>
            </ul>
          </li>
        </ol>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="wp-content">
      <div class="wp-container">

        <!-- Section 1: Executive Summary -->
        <section id="executive-summary" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">1.</span> {{ $t('whitepaper.section1.title') }}</h2>
          <p v-html="$t('whitepaper.section1.p1', html)"></p>
          <p v-html="$t('whitepaper.section1.p2', html)"></p>
          <p v-html="$t('whitepaper.section1.p3', html)"></p>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section1.capability1', html)"></li>
            <li v-html="$t('whitepaper.section1.capability2', html)"></li>
            <li v-html="$t('whitepaper.section1.capability3', html)"></li>
            <li v-html="$t('whitepaper.section1.capability4', html)"></li>
          </ul>
          <p>{{ $t('whitepaper.section1.p4') }}</p>
        </section>

        <!-- Section 2: Market Background -->
        <section id="market-background" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">2.</span> {{ $t('whitepaper.section2.title') }}</h2>

          <h3 id="market-2-1" class="wp-section__subtitle">{{ $t('whitepaper.section2.sub1.title') }}</h3>
          <p>{{ $t('whitepaper.section2.sub1.intro') }}</p>
          <div class="wp-card-grid">
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section2.sub1.card1Title') }}</h4>
              <p>{{ $t('whitepaper.section2.sub1.card1Text') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section2.sub1.card2Title') }}</h4>
              <p>{{ $t('whitepaper.section2.sub1.card2Text') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section2.sub1.card3Title') }}</h4>
              <p>{{ $t('whitepaper.section2.sub1.card3Text') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section2.sub1.card4Title') }}</h4>
              <p>{{ $t('whitepaper.section2.sub1.card4Text') }}</p>
            </div>
          </div>

          <h3 id="market-2-2" class="wp-section__subtitle">{{ $t('whitepaper.section2.sub2.title') }}</h3>
          <p>{{ $t('whitepaper.section2.sub2.intro') }}</p>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section2.sub2.pain1', html)"></li>
            <li v-html="$t('whitepaper.section2.sub2.pain2', html)"></li>
            <li v-html="$t('whitepaper.section2.sub2.pain3', html)"></li>
            <li v-html="$t('whitepaper.section2.sub2.pain4', html)"></li>
          </ul>

          <h3 id="market-2-3" class="wp-section__subtitle">{{ $t('whitepaper.section2.sub3.title') }}</h3>
          <p>{{ $t('whitepaper.section2.sub3.intro') }}</p>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section2.sub3.point1', html)"></li>
            <li v-html="$t('whitepaper.section2.sub3.point2', html)"></li>
            <li v-html="$t('whitepaper.section2.sub3.point3', html)"></li>
            <li v-html="$t('whitepaper.section2.sub3.point4', html)"></li>
          </ul>
          <p>{{ $t('whitepaper.section2.sub3.conclusion') }}</p>
        </section>

        <!-- Section 3: Solution -->
        <section id="solution" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">3.</span> {{ $t('whitepaper.section3.title') }}</h2>

          <h3 id="solution-3-1" class="wp-section__subtitle">{{ $t('whitepaper.section3.sub1.title') }}</h3>
          <p v-html="$t('whitepaper.section3.sub1.p1', html)"></p>
          <p>{{ $t('whitepaper.section3.sub1.p2') }}</p>
          <figure class="wp-figure">
            <img src="./images/solution-architecture.png" :alt="$t('whitepaper.section3.sub1.fig1Alt')" class="wp-figure__img" loading="lazy" />
            <figcaption class="wp-figure__caption">{{ $t('whitepaper.section3.sub1.fig1') }}</figcaption>
          </figure>

          <h3 id="solution-3-2" class="wp-section__subtitle">{{ $t('whitepaper.section3.sub2.title') }}</h3>
          <p>{{ $t('whitepaper.section3.sub2.intro') }}</p>
          <figure class="wp-figure">
            <img src="./images/technical-architecture.png" :alt="$t('whitepaper.section3.sub2.fig2Alt')" class="wp-figure__img" loading="lazy" />
            <figcaption class="wp-figure__caption">{{ $t('whitepaper.section3.sub2.fig2') }}</figcaption>
          </figure>
          <div class="wp-card-grid wp-card-grid--2">
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section3.sub2.blockchainTitle') }}</h4>
              <p>{{ $t('whitepaper.section3.sub2.blockchainText') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section3.sub2.storageTitle') }}</h4>
              <p>{{ $t('whitepaper.section3.sub2.storageText') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section3.sub2.aiTitle') }}</h4>
              <p>{{ $t('whitepaper.section3.sub2.aiText') }}</p>
            </div>
            <div class="wp-card">
              <h4 class="wp-card__title">{{ $t('whitepaper.section3.sub2.appTitle') }}</h4>
              <p>{{ $t('whitepaper.section3.sub2.appText') }}</p>
            </div>
          </div>

          <h3 id="solution-3-3" class="wp-section__subtitle">{{ $t('whitepaper.section3.sub3.title') }}</h3>
          <p>{{ $t('whitepaper.section3.sub3.p1') }}</p>
          <figure class="wp-figure">
            <img src="./images/value-circulation.png" :alt="$t('whitepaper.section3.sub3.fig3Alt')" class="wp-figure__img" loading="lazy" />
            <figcaption class="wp-figure__caption">{{ $t('whitepaper.section3.sub3.fig3') }}</figcaption>
          </figure>
          <p>{{ $t('whitepaper.section3.sub3.p2') }}</p>
        </section>

        <!-- Section 4: Core Features -->
        <section id="core-features" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">4.</span> {{ $t('whitepaper.section4.title') }}</h2>
          <p>{{ $t('whitepaper.section4.intro') }}</p>

          <h3 id="features-4-1" class="wp-section__subtitle">{{ $t('whitepaper.section4.ai.title') }}</h3>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.ai.matching.title') }}</h4>
          <p>{{ $t('whitepaper.section4.ai.matching.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.ai.agent.title') }}</h4>
          <p>{{ $t('whitepaper.section4.ai.agent.text') }}</p>

          <h3 id="features-4-2" class="wp-section__subtitle">{{ $t('whitepaper.section4.social.title') }}</h3>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.social.creation.title') }}</h4>
          <p>{{ $t('whitepaper.section4.social.creation.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.social.square.title') }}</h4>
          <p>{{ $t('whitepaper.section4.social.square.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.social.community.title') }}</h4>
          <p>{{ $t('whitepaper.section4.social.community.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.social.kol.title') }}</h4>
          <p>{{ $t('whitepaper.section4.social.kol.text') }}</p>

          <h3 id="features-4-3" class="wp-section__subtitle">{{ $t('whitepaper.section4.market.title') }}</h3>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.market.data.title') }}</h4>
          <p>{{ $t('whitepaper.section4.market.data.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.market.news.title') }}</h4>
          <p>{{ $t('whitepaper.section4.market.news.text') }}</p>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.market.research.title') }}</h4>
          <p>{{ $t('whitepaper.section4.market.research.text') }}</p>

          <h3 id="features-4-4" class="wp-section__subtitle">{{ $t('whitepaper.section4.socialfi.title') }}</h3>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.socialfi.toolkit.title') }}</h4>
          <p>{{ $t('whitepaper.section4.socialfi.toolkit.intro') }}</p>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section4.socialfi.toolkit.referral', html)"></li>
            <li v-html="$t('whitepaper.section4.socialfi.toolkit.creator', html)"></li>
            <li v-html="$t('whitepaper.section4.socialfi.toolkit.tipping', html)"></li>
            <li v-html="$t('whitepaper.section4.socialfi.toolkit.growth', html)"></li>
          </ul>
          <h4 class="wp-section__subsubtitle">{{ $t('whitepaper.section4.socialfi.wallet.title') }}</h4>
          <p>{{ $t('whitepaper.section4.socialfi.wallet.text') }}</p>

          <h3 id="features-4-5" class="wp-section__subtitle">{{ $t('whitepaper.section4.did.title') }}</h3>
          <p>{{ $t('whitepaper.section4.did.text') }}</p>
        </section>

        <!-- Section 5: Tokenomics -->
        <section id="tokenomics" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">5.</span> {{ $t('whitepaper.section5.title') }}</h2>
          <h3 id="token-5-1" class="wp-section__subtitle">{{ $t('whitepaper.section5.overview.title') }}</h3>
          <table class="wp-table">
            <tbody>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.tokenName') }}</td><td>{{ $t('whitepaper.section5.overview.tokenNameValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.projectType') }}</td><td>{{ $t('whitepaper.section5.overview.projectTypeValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.launchDate') }}</td><td>{{ $t('whitepaper.section5.overview.launchDateValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.totalSupply') }}</td><td>{{ $t('whitepaper.section5.overview.totalSupplyValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.inflation') }}</td><td>{{ $t('whitepaper.section5.overview.inflationValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.deflation') }}</td><td>{{ $t('whitepaper.section5.overview.deflationValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.decimals') }}</td><td>{{ $t('whitepaper.section5.overview.decimalsValue') }}</td></tr>
              <tr><td class="wp-table__label">{{ $t('whitepaper.section5.overview.blockchain') }}</td><td>{{ $t('whitepaper.section5.overview.blockchainValue') }}</td></tr>
            </tbody>
          </table>
          <h3 id="token-5-2" class="wp-section__subtitle">{{ $t('whitepaper.section5.allocation.title') }}</h3>
          <table class="wp-table wp-table--full">
            <thead>
              <tr><th>{{ $t('whitepaper.section5.allocation.thCategory') }}</th><th>{{ $t('whitepaper.section5.allocation.thShare') }}</th><th>{{ $t('whitepaper.section5.allocation.thAmount') }}</th><th>{{ $t('whitepaper.section5.allocation.thVesting') }}</th></tr>
            </thead>
            <tbody>
              <tr><td>{{ $t('whitepaper.section5.allocation.community') }}</td><td>35%</td><td>350M</td><td>{{ $t('whitepaper.section5.allocation.communityVesting') }}</td></tr>
              <tr><td>{{ $t('whitepaper.section5.allocation.investors') }}</td><td>20%</td><td>200M</td><td>{{ $t('whitepaper.section5.allocation.investorsVesting') }}</td></tr>
              <tr><td>{{ $t('whitepaper.section5.allocation.team') }}</td><td>16%</td><td>160M</td><td>{{ $t('whitepaper.section5.allocation.teamVesting') }}</td></tr>
              <tr><td>{{ $t('whitepaper.section5.allocation.ecosystem') }}</td><td>10%</td><td>100M</td><td>{{ $t('whitepaper.section5.allocation.ecosystemVesting') }}</td></tr>
              <tr><td>{{ $t('whitepaper.section5.allocation.liquidity') }}</td><td>10%</td><td>100M</td><td>{{ $t('whitepaper.section5.allocation.liquidityVesting') }}</td></tr>
              <tr><td>{{ $t('whitepaper.section5.allocation.reserve') }}</td><td>9%</td><td>90M</td><td>{{ $t('whitepaper.section5.allocation.reserveVesting') }}</td></tr>
            </tbody>
          </table>
          <h3 id="token-5-3" class="wp-section__subtitle">{{ $t('whitepaper.section5.utility.title') }}</h3>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section5.utility.creator', html)"></li>
            <li v-html="$t('whitepaper.section5.utility.governance', html)"></li>
            <li v-html="$t('whitepaper.section5.utility.fees', html)"></li>
            <li v-html="$t('whitepaper.section5.utility.nft', html)"></li>
            <li v-html="$t('whitepaper.section5.utility.ecosystem', html)"></li>
          </ul>
          <h3 id="token-5-4" class="wp-section__subtitle">{{ $t('whitepaper.section5.buyback.title') }}</h3>
          <p>{{ $t('whitepaper.section5.buyback.text') }}</p>
        </section>

        <!-- Section 6: Roadmap -->
        <section id="roadmap" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">6.</span> {{ $t('whitepaper.section6.title') }}</h2>
          <div class="wp-roadmap">
            <div class="wp-roadmap__item">
              <div class="wp-roadmap__year">{{ $t('whitepaper.section6.y2025.year') }}</div>
              <h3 class="wp-roadmap__phase">{{ $t('whitepaper.section6.y2025.phase') }}</h3>
              <div class="wp-roadmap__quarters">
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2025.q1') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2025.q1a') }}</li><li>{{ $t('whitepaper.section6.y2025.q1b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2025.q2') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2025.q2a') }}</li><li>{{ $t('whitepaper.section6.y2025.q2b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2025.q3') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2025.q3a') }}</li><li>{{ $t('whitepaper.section6.y2025.q3b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2025.q4') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2025.q4a') }}</li><li>{{ $t('whitepaper.section6.y2025.q4b') }}</li></ul></div>
              </div>
            </div>
            <div class="wp-roadmap__item">
              <div class="wp-roadmap__year">{{ $t('whitepaper.section6.y2026.year') }}</div>
              <h3 class="wp-roadmap__phase">{{ $t('whitepaper.section6.y2026.phase') }}</h3>
              <div class="wp-roadmap__quarters">
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2026.q1') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2026.q1a') }}</li><li>{{ $t('whitepaper.section6.y2026.q1b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2026.q2') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2026.q2a') }}</li><li>{{ $t('whitepaper.section6.y2026.q2b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2026.q3') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2026.q3a') }}</li><li>{{ $t('whitepaper.section6.y2026.q3b') }}</li></ul></div>
                <div class="wp-roadmap__q"><strong>{{ $t('whitepaper.section6.y2026.q4') }}</strong><ul class="wp-list"><li>{{ $t('whitepaper.section6.y2026.q4a') }}</li><li>{{ $t('whitepaper.section6.y2026.q4b') }}</li></ul></div>
              </div>
            </div>
            <div class="wp-roadmap__item">
              <div class="wp-roadmap__year">{{ $t('whitepaper.section6.y2027.year') }}</div>
              <h3 class="wp-roadmap__phase">{{ $t('whitepaper.section6.y2027.phase') }}</h3>
              <ul class="wp-list"><li>{{ $t('whitepaper.section6.y2027.a') }}</li><li>{{ $t('whitepaper.section6.y2027.b') }}</li><li>{{ $t('whitepaper.section6.y2027.c') }}</li><li>{{ $t('whitepaper.section6.y2027.d') }}</li></ul>
            </div>
            <div class="wp-roadmap__item">
              <div class="wp-roadmap__year">{{ $t('whitepaper.section6.y2028.year') }}</div>
              <h3 class="wp-roadmap__phase">{{ $t('whitepaper.section6.y2028.phase') }}</h3>
              <ul class="wp-list"><li>{{ $t('whitepaper.section6.y2028.a') }}</li><li>{{ $t('whitepaper.section6.y2028.b') }}</li><li>{{ $t('whitepaper.section6.y2028.c') }}</li></ul>
            </div>
          </div>
        </section>

        <!-- Section 7: Long-term Vision -->
        <section id="long-term-vision" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">7.</span> {{ $t('whitepaper.section7.title') }}</h2>
          <p v-html="$t('whitepaper.section7.p1', html)"></p>
          <p>{{ $t('whitepaper.section7.p2') }}</p>
          <p>{{ $t('whitepaper.section7.p3') }}</p>
          <ul class="wp-list">
            <li v-html="$t('whitepaper.section7.dir1', html)"></li>
            <li v-html="$t('whitepaper.section7.dir2', html)"></li>
            <li v-html="$t('whitepaper.section7.dir3', html)"></li>
            <li v-html="$t('whitepaper.section7.dir4', html)"></li>
          </ul>
          <p>{{ $t('whitepaper.section7.p4') }}</p>
          <p>{{ $t('whitepaper.section7.p5') }}</p>
        </section>

        <!-- Section 8: Team & Partnerships -->
        <section id="team" class="wp-section">
          <h2 class="wp-section__title"><span class="wp-section__number">8.</span> {{ $t('whitepaper.section8.title') }}</h2>
          <p>{{ $t('whitepaper.section8.text') }}</p>
        </section>

        <!-- Disclaimer -->
        <section id="disclaimer" class="wp-section wp-section--disclaimer">
          <h2 class="wp-section__title">{{ $t('whitepaper.disclaimer.title') }}</h2>
          <p>{{ $t('whitepaper.disclaimer.text') }}</p>
        </section>

      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'WhitepaperPage',
  metaInfo() {
    return {
      title: 'CryptoPulse Whitepaper',
    }
  },
  data() {
    return {
      html: {
        bold: '<strong>',
        boldEnd: '</strong>',
        web1Start: '<strong>',
        web1End: '</strong>',
        web2Start: '<strong>',
        web2End: '</strong>',
        web3Start: '<strong>',
        web3End: '</strong>',
        web4Start: '<strong>',
        web4End: '</strong>',
        aiStart: '<strong>',
        aiEnd: '</strong>',
        cpStart: '<strong>',
        cpEnd: '</strong>',
        emStart: '<em>',
        emEnd: '</em>',
      }
    }
  },
  computed: {
    tocItems() {
      return [
        { id: 'executive-summary', label: this.$t('whitepaper.tocItems.s1') },
        { id: 'market-background', label: this.$t('whitepaper.tocItems.s2'), children: [
          { id: 'market-2-1', label: this.$t('whitepaper.tocItems.s2_1') },
          { id: 'market-2-2', label: this.$t('whitepaper.tocItems.s2_2') },
          { id: 'market-2-3', label: this.$t('whitepaper.tocItems.s2_3') },
        ]},
        { id: 'solution', label: this.$t('whitepaper.tocItems.s3'), children: [
          { id: 'solution-3-1', label: this.$t('whitepaper.tocItems.s3_1') },
          { id: 'solution-3-2', label: this.$t('whitepaper.tocItems.s3_2') },
          { id: 'solution-3-3', label: this.$t('whitepaper.tocItems.s3_3') },
        ]},
        { id: 'core-features', label: this.$t('whitepaper.tocItems.s4'), children: [
          { id: 'features-4-1', label: this.$t('whitepaper.tocItems.s4_1') },
          { id: 'features-4-2', label: this.$t('whitepaper.tocItems.s4_2') },
          { id: 'features-4-3', label: this.$t('whitepaper.tocItems.s4_3') },
          { id: 'features-4-4', label: this.$t('whitepaper.tocItems.s4_4') },
          { id: 'features-4-5', label: this.$t('whitepaper.tocItems.s4_5') },
        ]},
        { id: 'tokenomics', label: this.$t('whitepaper.tocItems.s5'), children: [
          { id: 'token-5-1', label: this.$t('whitepaper.tocItems.s5_1') },
          { id: 'token-5-2', label: this.$t('whitepaper.tocItems.s5_2') },
          { id: 'token-5-3', label: this.$t('whitepaper.tocItems.s5_3') },
          { id: 'token-5-4', label: this.$t('whitepaper.tocItems.s5_4') },
        ]},
        { id: 'roadmap', label: this.$t('whitepaper.tocItems.s6') },
        { id: 'long-term-vision', label: this.$t('whitepaper.tocItems.s7') },
        { id: 'team', label: this.$t('whitepaper.tocItems.s8') },
        { id: 'disclaimer', label: this.$t('whitepaper.tocItems.disclaimer') },
      ]
    }
  },
  methods: {
    scrollTo(id) {
      const el = document.getElementById(id)
      if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' })
    }
  }
}
</script>

<style scoped>
.whitepaper-page { --cp-blue:#0082f3;--cp-blue-light:#2895f7;--cp-cyan:#00c6ff;--cp-bg:#f5f5f5;--cp-black:#191919;--cp-gray:#626262;--cp-white:#fff;--cp-border:#e5e7eb;--cp-radius:16px;font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--cp-black);background:var(--cp-white);-webkit-font-smoothing:antialiased; }
.wp-container { max-width:860px;margin:0 auto;padding:0 24px; }
.wp-hero { background:linear-gradient(135deg,#0a1628 0%,#0d2137 40%,#0f2b4a 100%);padding:100px 24px 80px;text-align:center;position:relative;overflow:hidden; }
.wp-hero::before { content:'';position:absolute;top:-50%;left:-50%;width:200%;height:200%;background:radial-gradient(circle at 30% 50%,rgba(0,130,243,0.08) 0%,transparent 50%),radial-gradient(circle at 70% 50%,rgba(0,198,255,0.06) 0%,transparent 50%);pointer-events:none; }
.wp-hero__inner { position:relative;z-index:1;max-width:720px;margin:0 auto; }
.wp-hero__title { font-size:3rem;font-weight:800;letter-spacing:0.15em;color:var(--cp-white);margin-bottom:8px; }
.wp-hero__subtitle { font-size:1.25rem;font-weight:300;letter-spacing:0.5em;color:rgba(255,255,255,0.6);margin-bottom:32px; }
.wp-hero__tagline { font-size:1.125rem;font-weight:600;color:var(--cp-cyan);margin-bottom:16px; }
.wp-hero__vision { font-size:0.95rem;color:rgba(255,255,255,0.7);line-height:1.7;max-width:600px;margin:0 auto 24px; }
.wp-hero__version { display:inline-block;padding:6px 20px;border:1px solid rgba(255,255,255,0.2);border-radius:999px;font-size:0.85rem;color:rgba(255,255,255,0.5);letter-spacing:0.05em; }
.wp-toc { background:var(--cp-bg);padding:48px 24px;border-bottom:1px solid var(--cp-border); }
.wp-toc__title { font-size:1.5rem;font-weight:700;color:var(--cp-black);margin-bottom:24px; }
.wp-toc__list { list-style:none;padding:0;margin:0;columns:2;column-gap:48px; }
.wp-toc__item { break-inside:avoid;margin-bottom:8px; }
.wp-toc__link { color:var(--cp-blue);text-decoration:none;font-size:0.95rem;line-height:1.8;transition:color 0.2s; }
.wp-toc__link:hover { color:var(--cp-cyan);text-decoration:underline; }
.wp-toc__sublist { list-style:none;padding-left:20px;margin:0; }
.wp-toc__subitem { margin-bottom:4px; }
.wp-toc__subitem .wp-toc__link { font-size:0.875rem;color:var(--cp-gray); }
.wp-toc__subitem .wp-toc__link:hover { color:var(--cp-blue); }
.wp-content { padding:24px 0 80px; }
.wp-section { padding:48px 0;border-bottom:1px solid var(--cp-border); }
.wp-section:last-child { border-bottom:none; }
.wp-section__title { font-size:1.75rem;font-weight:700;color:var(--cp-black);margin-bottom:24px;padding-bottom:12px;border-bottom:3px solid var(--cp-blue);display:inline-block; }
.wp-section__number { color:var(--cp-blue);margin-right:4px; }
.wp-section__subtitle { font-size:1.25rem;font-weight:600;color:var(--cp-black);margin:36px 0 16px; }
.wp-section__subsubtitle { font-size:1.05rem;font-weight:600;color:var(--cp-gray);margin:24px 0 12px; }
.wp-section p { font-size:0.95rem;line-height:1.8;color:var(--cp-gray);margin-bottom:16px; }
.wp-section--disclaimer { background:var(--cp-bg);border-radius:var(--cp-radius);padding:32px;margin-top:24px; }
.wp-section--disclaimer .wp-section__title { border-bottom-color:#dc2626; }
.wp-list { list-style:none;padding:0;margin:0 0 16px; }
.wp-list li { position:relative;padding-left:20px;margin-bottom:10px;font-size:0.95rem;line-height:1.7;color:var(--cp-gray); }
.wp-list li::before { content:'';position:absolute;left:0;top:10px;width:6px;height:6px;border-radius:50%;background:var(--cp-blue); }
.wp-card-grid { display:grid;grid-template-columns:1fr 1fr;gap:16px;margin:20px 0; }
.wp-card { background:var(--cp-bg);border-radius:var(--cp-radius);padding:24px;border:1px solid var(--cp-border);transition:box-shadow 0.2s; }
.wp-card:hover { box-shadow:0 4px 20px rgba(0,130,243,0.08); }
.wp-card__title { font-size:1rem;font-weight:600;color:var(--cp-black);margin-bottom:8px; }
.wp-card p { font-size:0.875rem;line-height:1.7;color:var(--cp-gray);margin:0; }
.wp-figure { margin:32px 0;text-align:center; }
.wp-figure__img { max-width:100%;height:auto;border-radius:var(--cp-radius);border:1px solid var(--cp-border); }
.wp-figure__caption { margin-top:12px;font-size:0.85rem;color:var(--cp-gray);font-style:italic; }
.wp-table { width:100%;border-collapse:collapse;margin:20px 0;font-size:0.9rem;overflow:hidden;border:1px solid var(--cp-border); }
.wp-table th,.wp-table td { padding:12px 16px;text-align:left;border-bottom:1px solid var(--cp-border); }
.wp-table th { background:var(--cp-blue);color:var(--cp-white);font-weight:600;font-size:0.85rem; }
.wp-table td { color:var(--cp-gray); }
.wp-table__label { font-weight:600;color:var(--cp-black);background:var(--cp-bg);width:180px; }
.wp-table tbody tr:hover { background:rgba(0,130,243,0.03); }
.wp-table--full { table-layout:auto; }
.wp-roadmap { position:relative;padding-left:32px; }
.wp-roadmap::before { content:'';position:absolute;left:8px;top:0;bottom:0;width:3px;background:linear-gradient(to bottom,var(--cp-blue),var(--cp-cyan));border-radius:2px; }
.wp-roadmap__item { position:relative;margin-bottom:40px; }
.wp-roadmap__item::before { content:'';position:absolute;left:-28px;top:6px;width:14px;height:14px;background:var(--cp-blue);border-radius:50%;border:3px solid var(--cp-white);box-shadow:0 0 0 2px var(--cp-blue); }
.wp-roadmap__year { display:inline-block;background:var(--cp-blue);color:var(--cp-white);font-weight:700;font-size:0.85rem;padding:4px 14px;border-radius:999px;margin-bottom:8px; }
.wp-roadmap__phase { font-size:1.1rem;font-weight:600;color:var(--cp-black);margin-bottom:12px; }
.wp-roadmap__quarters { display:flex;flex-direction:column;gap:12px; }
.wp-roadmap__q { background:var(--cp-bg);border-radius:12px;padding:16px;border-left:3px solid var(--cp-blue); }
.wp-roadmap__q strong { display:block;margin-bottom:8px;color:var(--cp-black);font-size:0.9rem; }
@media (max-width:768px) {
  .wp-hero__title { font-size:2rem;letter-spacing:0.08em; }
  .wp-hero__subtitle { font-size:0.9rem;letter-spacing:0.3em; }
  .wp-hero { padding:60px 16px 48px; }
  .wp-toc__list { columns:1; }
  .wp-card-grid { grid-template-columns:1fr; }
  .wp-section__title { font-size:1.35rem; }
  .wp-table__label { width:130px; }
  .wp-container { padding:0 16px; }
}
</style>
