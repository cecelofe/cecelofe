const puppeteer = require('puppeteer');

(async () => {
  // Iniciar o navegador
  const browser = await puppeteer.launch();

  // Abrir uma nova página
  const page = await browser.newPage();

  // Navegar até o site
  await page.goto('https://www.example.com');

  // Localizar os elementos de entrada (exemplo: campos de login e senha)
  await page.type('input[name="username"]', 'seu_usuario');
  await page.type('input[name="password"]', 'sua_senha');

  // Enviar o formulário de login
  await page.keyboard.press('Enter');

  // Aguardar alguns segundos para o login ser concluído
  await page.waitForTimeout(5000);

  // Seu código adicional para interagir com o site após o login...

  // Fechar o navegador
  await browser.close();
})();
