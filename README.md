<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quadratic Solver & Grade Converter</title>
</head>
<body>
    <h1>Quadratic Equation Solver</h1>
    <input id="a" placeholder="a"> <input id="b" placeholder="b"> <input id="c" placeholder="c">
    <button onclick="solveQuadratic()">Solve</button>
    <p id="quadraticResult"></p>

    <h1>Grade Converter</h1>
    <input id="score" placeholder="Numeric Score (0-100)">
    <button onclick="convertGrade()">Convert</button>
    <p id="gradeResult"></p>

    <script src="script.js"></script>
</body>
</html>
function solveQuadratic() {
    const a = parseFloat(document.getElementById('a').value);
    const b = parseFloat(document.getElementById('b').value);
    const c = parseFloat(document.getElementById('c').value);
    const discriminant = b*b - 4*a*c;
    let result;
    if (discriminant > 0) {
        const root1 = (-b + Math.sqrt(discriminant)) / (2*a);
        const root2 = (-b - Math.sqrt(discriminant)) / (2*a);
        result = `Roots: ${root1}, ${root2}`;
    } else if (discriminant === 0) {
        const root = -b / (2*a);
        result = `Root: ${root}`;
    } else {
        result = "No real roots";
    }
    document.getElementById('quadraticResult').innerText = result;
}

function convertGrade() {
    const score = parseFloat(document.getElementById('score').value);
    let grade;
    if (score >= 85) grade = 'A+';
    else if (score >= 75) grade = 'A';
    else if (score >= 68) grade = 'B+';
    else if (score >= 60) grade = 'B';
    else if (score >= 55) grade = 'C+';
    else if (score >= 50) grade = 'C';
    else grade = 'D';
    document.getElementById('gradeResult').innerText = `Grade: ${grade}`;
}
