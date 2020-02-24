<template>
  <div class="container">
    <Header />
    <div
      id="home"
      class="legend-img flex-center pull-start flex-column std-padding legend-section-height"
    >
      <div class="lengend-img__content stack">
        <h1 class="white-text">
          POPIA is coming.
          <br />
          <br />
          All organisations will have to comply
        </h1>
        <h3 class="white-text">
          Our service will enable you to make your clients compliant
        </h3>
      </div>
    </div>
    <div
      class="std-y-padding std-padding card-section flex-column flex-center pull-start stack"
    >
      <h2 class="white-text">POPIA365 allows your clients to:</h2>
      <div class="card-section__card-container">
        <CardWithHeader
          v-for="(item, index) in cardItems"
          :key="`${index}-cardItem`"
          :heading="item.heading"
          :list="item.list"
        />
      </div>
      <h3 class="card-section__post-heading white-text">
        Pricing plans from professional companies to enterprise.
      </h3>
    </div>
    <div id="features" class="std-padding std-y-padding stack-2p5">
      <h1>Software Features</h1>
      <div class="grid-large-right align-center">
        <div class="stack-2p5">
          <div class="stack">
            <h2>Home Screen</h2>
            <p>
              Home screen with all functionality available. Work in a logical
              sequence.
            </p>
          </div>
          <div class="stack">
            <h3>Section 1</h3>
            <div class="half-stack">
              <TextWithCircleCheck
                v-for="(feature, index) in softwareFeatures.sectionOne"
                :key="`${index}-feature-one`"
                :feature="feature"
              />
            </div>
          </div>
          <div class="stack">
            <h3>Section 2</h3>
            <div class="half-stack">
              <TextWithCircleCheck
                v-for="(feature, index) in softwareFeatures.sectionTwo"
                :key="`${index}-feature-two`"
                :feature="feature"
              />
            </div>
          </div>
          <div class="stack">
            <h3>Section 3</h3>
            <div class="half-stack">
              <TextWithCircleCheck
                v-for="(feature, index) in softwareFeatures.sectionThree"
                :key="`${index}-feature-three`"
                :feature="feature"
              />
            </div>
          </div>
        </div>
        <div>
          <img src="~/assets/images/homepage.png" class="max-w-100" />
        </div>
      </div>
    </div>
    <div class="std-padding std-y-padding grid-large-left background-grey">
      <div><img src="~/assets/images/compliance.png" class="max-w-100" /></div>
      <div class="stack">
        <h2>Compliance Section</h2>
        <div class="half-stack">
          <TextWithCircleCheck
            v-for="(feature, index) in complianceSection"
            :key="`${index}-compliance-feature`"
            :feature="feature"
          />
        </div>
      </div>
    </div>
    <div class="std-padding std-y-padding grid-even">
      <div class="stack">
        <h2>Compliance Items</h2>
        <div class="half-stack">
          <TextWithCircleCheck
            v-for="(feature, index) in complianceItems"
            :key="`${index}-compliance-item`"
            :feature="feature"
          />
        </div>
      </div>
      <div>
        <img src="~/assets/images/compliance-items.png" class="max-w-100" />
      </div>
    </div>
    <div class="std-padding std-y-padding grid-large-left background-grey">
      <div>
        <img src="~/assets/images/data-mapping.png" class="max-w-100" />
      </div>
      <div class="stack">
        <h2>Data Mapping</h2>
        <div class="half-stack">
          <TextWithCircleCheck
            v-for="(feature, index) in dataMapping"
            :key="`${index}-data-mapping`"
            :feature="feature"
          />
        </div>
      </div>
    </div>
    <div class="std-margin std-y-padding grid-even border-bottom">
      <div class="stack">
        <h2>Dynamic Dashboard</h2>
        <div class="half-stack">
          <TextWithCircleCheck
            v-for="(feature, index) in dynamicDashboard"
            :key="`${index}-compliance-item`"
            :feature="feature"
          />
        </div>
      </div>
      <div>
        <img src="~/assets/images/dynamic-dashboards.png" class="max-w-100" />
      </div>
    </div>
    <div id="partner" class="std-padding std-y-padding stack">
      <h1>Partner with us</h1>
      <p>
        If you are looking for the service for your organisation, contact us and
        we will refer a partner to assist you. We work exclusively through a
        partner network. Our partners are privacy professionals who can provide
        the necessary assistance and onboarding.
      </p>
      <h2>Benefits of partnering with us</h2>
      <div class="card-section__card-container">
        <CardWithHeader
          v-for="(item, index) in partnerBenefits"
          :key="`${index}-benefit`"
          :heading="item.heading"
          :list="item.list"
          :strongShadow="true"
        />
      </div>
    </div>
    <div
      id="contact"
      class="grid-even contact-section std-padding std-y-padding white-text"
    >
      <div class="stack">
        <h2>Contact Us</h2>
        <div class="half-stack">
          <p>
            Contact us to become a partner, OR if you wish to have us refer a
            partner to you.
          </p>
          <p>
            We will contact you and provide you with a demonstration of our
            service and discuss how best you can partner with us.
          </p>
        </div>
        <div class="half-stack flex-column flex-start pull-start">
          <label for="fname">First Name</label>
          <input type="text" name="fname" id="fname" class="std-input" />
        </div>
        <div class="half-stack flex-column flex-start pull-start">
          <label for="lname">Last Name</label>
          <input type="text" name="lname" id="lname" class="std-input" />
        </div>
        <div class="half-stack flex-column flex-start pull-start">
          <label for="message">Message (Optional)</label>
          <textarea
            type="text"
            name="message"
            id="message"
            class="std-input"
          ></textarea>
        </div>
        <button type="submit">
          Submit
        </button>
      </div>
      <div></div>
    </div>
  </div>
</template>

<script>
//
// ----------------------- Components -----------------------
import TextWithCircleCheck from "../components/TextWithCircleCheck.vue";
import CardWithHeader from "../components/CardWithHeader.vue";
import Header from "../components/Header.vue";
//
// ----------------------- Enums -----------------------
import { repeatableLists } from "../init/lib/repeatableLists";

export default {
  components: { Header, CardWithHeader, TextWithCircleCheck },
  data() {
    return {
      ...repeatableLists
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/css/partials/_variables.scss";
@import "../assets/css/partials/_mixins.scss";

.border-bottom {
  border-bottom: 1px solid #eaebec;
}

.background-grey {
  background-color: $lightgrey;
}

.card-section__post-heading {
  align-self: center;
}

.card-section {
  background-color: $dark-blue;
}

.container {
  overflow: hidden;
}

.legend-img {
  width: 100%;
  background-image: url(~assets/images/legend/main-img.png);

  .lengend-img__content {
    max-width: 35rem;
  }
}

.card-section__card-container {
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 1rem;
  min-width: 100%;

  @include breakpoint($medium) {
    grid-template-columns: 1fr 1fr;
  }

  @include breakpoint($large) {
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}

.contact-section {
  background-color: $dark-blue;
}

button[type="submit"] {
  width: 160px;
  height: 45px;
  background-color: #838994;
  font-family: inherit;
  font-size: 1rem;
  border: 0;
}
</style>
