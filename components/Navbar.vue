<template>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navbar mit Suchfeld</title>
</head>
<body class="bg-gray-100">
  <nav class="bg-gray-800 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div class="text-white font-bold text-xl">Logo</div>
      <div class="flex items-center">
        <input class="rounded-l-lg bg-white px-4 py-2 focus:outline-none focus:ring focus:border-blue-300" type="text" placeholder="Suchen...">
        <button class="bg-blue-500 hover:bg-blue-600 text-white font-semibold px-4 py-2 rounded-r-lg focus:outline-none focus:ring focus:border-blue-300">
          Suchen
        </button>
      </div>
    </div>
  </nav>
</body>
</template>
