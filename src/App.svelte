<script lang="ts">
  import { default as exerciseList } from './exercise-list.json'

  const difficulties = ['Beginner', 'Intermediate', 'Advanced', 'Pro']
</script>

<main>
    <h1>Calisthenics Exercises</h1>

    <div class="row">
        {#each exerciseList as exercise}
            <div class="exercise">
                <div class="title">
                    {exercise.name}
                </div>

                <div class="difficulty">
                    {#each difficulties as difficulty, index}
                        <svg class={"icon " + (index <= difficulties.indexOf(exercise.difficulty) ? 'fill' : '')}
                             xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512.009 512.009">
                            <path d="M441.071 192.046l-3.729-.042c-51.917 0-98.948 28.75-122.781 74.156-14.875-6.656-31.115-10.156-47.885-10.156-16.856 0-33.055 3.759-47.872 10.45-3.969 1.792-6.307 6.005-5.977 10.348.28 3.691.516 7.397.516 11.202 0 17.385-3.5 33.323-10.396 47.365a10.663 10.663 0 01-9.583 5.969c-1.573 0-3.177-.354-4.688-1.094-5.292-2.594-7.469-8.99-4.875-14.271 5.448-11.104 8.208-23.875 8.208-37.969 0-7.82-1.664-28.522-1.947-31.085-1.01-9.141-2.26-18.068-3.46-26.405-.003-.021.007-.04.004-.061-1.987-13.837-3.921-27.276-4.046-38.46l53.933.01a32.007 32.007 0 0022.639-9.375l42.667-42.667c12.198-12.198 12.469-31.875.813-44.406 5.567-8.46 6.936-19.292 2.973-29.469-2.49-6.395-7.326-11.625-13.037-15.431l-24.843-16.558c-11.443-7.627-24.744-12.292-38.489-12.705-32.731-.985-63.653 11.306-86.698 34.351-40.864 40.865-73.02 87.657-95.603 139.084-27.208 61.958-41 107.667-41 135.844 0 16.146-1.396 29.26-4.156 38.99-5.896 20.781 3.385 42.948 22.563 53.906 76.823 43.896 164.198 67.104 252.677 67.104h15.427a509.34 509.34 0 00161.674-26.34l6.857-2.295c30.495-10.208 51.052-38.766 51.052-70.925V266.765c0-40.167-31.823-73.688-70.938-74.719z"/>
                        </svg>
                    {/each}
                </div>

                <img draggable="false" class="image" src={exercise.image} alt={exercise.name}>
            </div>
        {/each}
    </div>
</main>

<style type="text/scss">
  $bright-red: #DE354C;
  $deepRed: #932432;
  $purePurple: #3C1874;
  $purpleTingedGrey: #283747;
  $cloud: #F3F3F3;

  main {
    margin: 0;
    padding-top: 2rem;

    background-color: $purpleTingedGrey;
    color: $cloud;

    h1 {
      text-align: center;
    }

    .row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;

      .exercise {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        width: 250px;
        height: 250px;

        margin-bottom: 2rem;

        .title {
          margin-top: 1rem;
          margin-bottom: 1rem;
          font-weight: 600;
        }

        .difficulty {
          .icon {
            width: 15px;
            height: 15px;
            margin: 0 .25rem 1rem;
            fill: $cloud;

            &.fill {
              fill: $deepRed;
            }
          }
        }

        .image {
          height: 150px;
        }
      }
    }
  }
</style>
