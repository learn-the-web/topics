---
layout: checklist
title: "Usability testing checklist"
tags: "web application usability user testing prototype task flows scenarios observations check list"
desc: "A check list of things to confirm we’re usability testing everything necessary in our websites."

sections:
  - title: 'Testing setup'
    notes: 'Get everything ready for usability testing so the participant’s experience is seemless.'
    groups:
      - title: 'Define testing objectives'
        notes: "Figure out what you’re testing and why that scenario needs to be tested."
        items:
          - 'Uncover usability problems?'
          - 'Find friction within a task flow?'
          - 'Validate your design decisions?'
          - 'See first user experience with fresh eyes?'
          - 'See if the target audience understands your value proposition?'
          - 'Determine if you messaging is understood?'

      - title: 'Determine flows & scenarios'
        notes: 'Figure out what scenarios and flows should be tested.'
        items:
          - 'Decide what screens & elements that need to be tested'
          - 'Are you testing multiple flows?'
          - 'Are you concentrating on a single flow?'
          - 'Should a single user execute multiple scenarios?'
          - 'Be aware that participants might need time to acclimate to the product'
          - 'Be aware of energy level considerations'

      - title: 'Identify devices'
        notes: 'Define the device & technology necessary to execute the tests.'
        items:
          - 'Consider assistive technology needs'
          - 'Encourage the participant to become familiar with the setup'
          - 'What devices? Mobile? Laptop? Desktop? Assistive technology?'
          - 'Use your device or the user’s device?'
          - 'Should the sound be be turned on?'

      - title: 'Draft instructions'
        notes: 'Pre-plan the instructions for participants in plain language.'
        items:
          - 'Use plain language'
          - 'Be prepared to offer instructions in different formats'
          - 'Be overly clear on the instructions'
          - 'Will participants need login credentials?'
          - 'Shorten links if they are unwieldy to type'
          - 'Slightly adjust the questions based on user’s natural experiences'

      - title: 'Find participants'
        notes: 'Determine what people would be helpful participants.'
        items:
          - 'Identify 5–7 participants'
          - 'Include people with disabilities'
          - 'Should you test your exact target market?'
          - 'Should you test with a random sample of people?'
          - 'Provide consent forms ahead of time'

      - title: 'Minimize bias'
        notes: 'Try to avoid skewing the results with your personal opinions.'
        items:
          - 'Don’t ask “yes/no” questions'
          - 'Use neutral questions that don’t lead an answer'
          - 'Tell scenarios in the user’s point of view: “Imagine you want to track the books you’re reading…”'
          - 'Don’t give hints or clues'
          - 'If you’re using scaled responses make the rating balanced'

  - title: 'Observe participants'
    notes: 'Observe the tests and listen for their feedback.'
    groups:
      - title: 'Observation results document'
        notes: 'Use a copy of this document for every task & scenario to be tested.'
        notCheckList: true
        width: 'full'
        items:
          - |
            <div class="table-wrapper scrollable">
              <table>
                <tr>
                  <th scope="row" colspan="3" rowspan="2" class="valign-bottom"><label for="task">Task</label></th>
                  <td scope="row" colspan="9" rowspan="2" class="valign-bottom"><input id="task"></td>
                  <th scope="row" colspan="3"><label for="project">Project</label></th>
                  <td colspan="9"><input id="project"></td>
                </tr>
                <tr>
                  <th scope="row" colspan="3"><label for="facilitator">Facilitator</label></th>
                  <td colspan="9"><input id="facilitator"></td>
                </tr>
              </table>

              <table>
                <thead>
                  <tr>
                    <th scope="row">№</th>
                    <th colspan="6" scope="row" id="table-user">User</th>
                    <th colspan="13" scope="row" id="table-observations">Facilitator observations</th>
                    <th colspan="13" scope="row" id="table-feedback">Participant feedback</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <th scope="col">1</th>
                    <td colspan="6"><textarea aria-labelledby="table-user"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-observations"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-feedback"></textarea></td>
                  </tr>
                  <tr>
                    <th scope="col">2</th>
                    <td colspan="6"><textarea aria-labelledby="table-user"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-observations"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-feedback"></textarea></td>
                  </tr>
                  <tr>
                    <th scope="col">3</th>
                    <td colspan="6"><textarea aria-labelledby="table-user"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-observations"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-feedback"></textarea></td>
                  </tr>
                  <tr>
                    <th scope="col">4</th>
                    <td colspan="6"><textarea aria-labelledby="table-user"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-observations"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-feedback"></textarea></td>
                  </tr>
                  <tr>
                    <th scope="col">5</th>
                    <td colspan="6"><textarea aria-labelledby="table-user"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-observations"></textarea></td>
                    <td colspan="13"><textarea aria-labelledby="table-feedback"></textarea></td>
                  </tr>
                </tbody>
              </table>
            </div>
---
