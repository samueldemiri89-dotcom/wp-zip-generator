<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<title>Scarica ZIP sito</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
</head>
<body>
<h2>Genera e scarica il ZIP del sito</h2>
<button id="downloadBtn">Scarica ZIP</button>

<script>
document.getElementById("downloadBtn").addEventListener("click", async () => {
    const zip = new JSZip();

    const indexHtml = `<!-- Qui dentro metti il contenuto di index.html -->`;
    const hvalaHtml = `<!-- Qui dentro metti il contenuto di hvala.html -->`;

    zip.file("index.html", indexHtml);
    zip.file("hvala.html", hvalaHtml);

    const content = await zip.generateAsync({type:"blob"});
    const link = document.createElement("a");
    link.href = URL.createObjectURL(content);
    link.download = "najbolja-usluga-kontejnera.zip";
    link.click();
});
</script>
</body>
</html>
