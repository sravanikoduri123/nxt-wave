# nxt-wave
toggle wave

let skillList = [{
        skillName: "HTML",
        uniqueNo: 1,
    },
    {
        skillName: "CSS",
        uniqueNo: 2,
    },
    {
        skillName: "JavaScript",
        uniqueNo: 3,
    }
];

let skillListContainerE1 = document.getElementById("skillListContainer");

function onMarkSkill(labelId) {
    let labelE1 = document.getElementById(labelId);
    labelE1.classList.toggle("selected");
}

function createAndAppendSkill(skill) {
    let checkboxId = "checkbox" + skill.uniqueNo;
    let labelId = "label" + skill.uniqueNo;

    let skillE1 = document.createElement("li");
    skillE1.classList.add("p-1");
    skillListContainerE1.appendChild(skillE1);

    let checkBoxE1 = document.createElement("input");
    checkBoxE1.type = "checkbox";
    checkBoxE1.id = checkboxId;

    checkBoxE1.onclick = function() {
        onMarkSkill(labelId);
    };
    skillE1.appendChild(checkBoxE1);

    let labelE1 = document.createElement("label");
    labelE1.setAttribute("for", checkboxId);
    labelE1.classList.add("checkbox-label");
    labelE1.id = labelId;
    labelE1.textContent = skill.skillName;
    skillE1.appendChild(labelE1);
}

for (let skill of skillList) {
    createAndAppendSkill(skill);
}
