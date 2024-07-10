const http = require('http');

const server = http.createServer((req, res) => {
  if (req.method === 'GET' && req.url === '/server') {
    const clientIp = req.headers['x-forwarded-for'] || req.connection.remoteAddress;
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end(`Client IP: ${clientIp}`);
  } else {
    res.writeHead(404, {'Content-Type': 'text/plain'});
    res.end('Not Found');
  }
});

const PORT = process.env.PORT || 3000;
server.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
