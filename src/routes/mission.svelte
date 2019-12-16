<style>
  #hero-image {
    width: 100%;
    position: relative;
  }

  #hero-image img {
    width: 100%;
  }

  #hero-image::before {
    content: "";
    background-color: var(--main-secondary-variant);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  .hero-image__title {
    position: absolute;
    top: 45%;
    text-align: center;
    width: 100%;
    font-weight: 900;
    color: white;
  }

  #mission-statement {
    color: #fff;
    background-color: var(--main-color);
    padding: 1.2rem;
  }

  #mission-statement > div {
    text-align: center;
  }

  #mission-statement > div > h4 {
    padding: 1.2rem auto;
  }

  #mission-statement > div > div {
    margin-top: 1rem;
  }

  #mission-statement p {
    margin-bottom: 1rem;
  }

  #content {
    margin: 1rem 1rem;
  }

  #title {
    margin: 0 0 1.2rem 0;
  }

  ul {
    margin: 0.9rem 0.5rem 0;
  }

  li {
    position: relative;
  }

  li::before {
    content: "*";
    position: absolute;
    left: -0.6rem;
    top: 2px;
  }

  @media (min-width: 480px) {
    #mission-statement > div {
      width: 70%;
      margin: auto;
    }
    #hero-image {
      height: 35vh;
      width: 100%;
    }

    #hero-image img {
      height: 100%;
    }

    .hero-image__title {
      font-size: 2rem;
    }

    #content {
      width: 70%;
      margin: 2rem auto;
    }

    li::before {
      content: "*";
      position: absolute;
      left: -1.2rem;
      top: 2px;
    }
  }
</style>

<svelte:head>
  <title>Mission Page</title>
</svelte:head>

<section id="hero-image">
  <img src="./mission-01.jpg" alt="School Attendance" />
  <div class="hero-image__title">MISSION</div>
</section>

<section id="mission-statement">
  <div class="content">
    <h4>MISSION STATEMENT</h4>
    <div>
      <p>
        To equip and prepare our students to withstand the winds of change
        during their formative years and to acquire knowledge and skills which
        will enable them to attain mastery in their chosen sphere when they step
        out into a wider arena.
      </p>
      <p>
        To fortify values which strengthen character that will stand true even
        in the most trying situations in the laboratory of practical adult life.
      </p>
      <p>
        To inculcate basic personal and professional values and produce
        successful leaders for our swiftly changing planet, in tune with
        international demands and requirements.
      </p>
    </div>
  </div>
</section>

<section id="content">
  <h4 id="title">MISSION AND OBJECTIVES</h4>
  <div>
    <strong>
      The objective of our institution is to create an effective schooling
      system by :
      <ul>
        <li>
          Exposing children to a variety of situations and experiences, which
          will prepare them to interact positively.
        </li>
        <li>
          Developing in students an attitude to self-learning and selfdirected
          learning for entering general as well as vocational streams of
          education.
        </li>
        <li>
          Providing the students with the latest hi-tech facilities that
          facilitate optimum learning with minimum effort with the help of
          electronic and satellite communication media.
        </li>
        <li>
          Including high level skills and competence required for achieving
          vocational development and entrepreneurship skills.
        </li>
        <li>
          Creating an awareness among students with the help of the curriculum
          about their role in the society and to making each of our students a
          complete individual with a well-balanced personality.
        </li>
        <li>
          Giving opportunities to all students, irrespective of their social and
          intellectual standing to excel in all fields of development.
        </li>
        <li>
          Fostering in students a sense of pride in our culture and heritage.
        </li>
        <li>
          Building and effective and highly engaged community among students,
          staff and the parent community.
        </li>
        <li>
          Encouraging an inclusive environment and inculcating teamwork and
          healthy competition among our students.
        </li>
        <li>
          Providing students & parents with an exclusive nature cum health club
          facility with all modern amenities.
        </li>
      </ul>
    </strong>
  </div>
</section>
