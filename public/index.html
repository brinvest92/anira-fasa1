const express = require('express');
const fs = require('fs');
const path = require('path');
const bodyParser = require('body-parser');

const app = express();
const PORT = process.env.PORT || 3000;
const dataPath = path.join(__dirname, 'data.json');

// Middleware
app.use(bodyParser.json());
app.use(express.static(path.join(__dirname, '..', 'public')));

// Routes
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, '..', 'public', 'index.html'));
});

// Get all data
app.get('/api/data', (req, res) => {
    fs.readFile(dataPath, 'utf8', (err, data) => {
        if (err) {
            console.error('Error reading data.json:', err);
            res.status(500).send('Error reading data');
        } else {
            res.json(JSON.parse(data));
        }
    });
});

// Add new entry
app.post('/api/data', (req, res) => {
    const formData = req.body;

    // Validate and sanitize inputs if necessary

    // Read existing data from data.json
    fs.readFile(dataPath, 'utf8', (err, data) => {
        if (err) {
            console.error('Error reading data.json:', err);
            res.status(500).send('Error reading data');
        } else {
            const jsonData = JSON.parse(data);

            // Check if unit and jalan already exist
            const existingEntry = jsonData.find(entry => entry.unit === formData.unit && entry.jalan === formData.jalan);
            if (existingEntry) {
                res.status(400).send('Unit and Jalan combination already exists');
            } else {
                // Add new entry
                jsonData.push(formData);

                // Write updated data back to data.json
                fs.writeFile(dataPath, JSON.stringify(jsonData, null, 2), 'utf8', (err) => {
                    if (err) {
                        console.error('Error writing data.json:', err);
                        res.status(500).send('Error updating data');
                    } else {
                        res.status(200).send('Form submission successful');
                    }
                });
            }
        }
    });
});

// Update nama field
app.put('/api/data/:unit/:jalan', (req, res) => {
    const { unit, jalan } = req.params;
    const updatedNama = req.body.nama;

    // Read existing data from data.json
    fs.readFile(dataPath, 'utf8', (err, data) => {
        if (err) {
            console.error('Error reading data.json:', err);
            res.status(500).send('Error reading data');
        } else {
            const jsonData = JSON.parse(data);

            // Find the entry to update
            const updatedData = jsonData.map(entry => {
                if (entry.unit === unit && entry.jalan === jalan) {
                    return {
                        ...entry,
                        nama: updatedNama
                    };
                } else {
                    return entry;
                }
            });

            // Write updated data back to data.json
            fs.writeFile(dataPath, JSON.stringify(updatedData, null, 2), 'utf8', (err) => {
                if (err) {
                    console.error('Error writing data.json:', err);
                    res.status(500).send('Error updating data');
                } else {
                    res.status(200).send('Nama updated successfully');
                }
            });
        }
    });
});

// Handle other routes
app.use((req, res) => {
    res.status(404).send('Not Found');
});

// Start server
app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});
