# Web.32.html
<!DOCTYPE html>
<html>
<head>
    <title>data saya</title>
    <style>
        body { 
            font-family: Arial; 
            background: white; 
            padding: 20px; 
        }

        .putih { 
            max-width: 500px; 
            margin: auto; 
            background: white; 
            padding: 20px; 
        }

        h1 { 
            font-size: 28px; 
            text-align: center; 
            margin: 10px 0; 
        }

        .foto { 
            width: 120px; 
            height: 120px; 
            border: 2px solid black; 
            margin: 10px auto; 
            background: #ccc; 
            overflow: hidden; 
        }

        #gambar { 
            width: 100%; 
            height: 100%; 
            object-fit: cover; 
        }

        .btn { 
            background: silver; 
            border: 2px solid black; 
            padding: 8px 20px; 
            display: inline-block; 
            margin: 10px 0; 
            cursor: pointer; 
        }

        .btn:active { 
            background: gray; 
        }

        input { 
            display: none; 
        }

        p { 
            font-size: 18px; 
            margin: 12px 0; 
            padding: 5px; 
        }

        .label { 
            display: inline-block; 
            width: 80px; 
            font-weight: bold; 
        }
    </style>
</head>
<body>
    <div class="putih">
        <h1>BIODATA</h1>

        <div class="foto">
            <img id="gambar" src="data:image/svg+xml,%3Csvg width='120' height='120'%3E%3Crect width='120' height='120' fill='%23999'/%3E%3Ctext x='30' y='65' fill='black'%3EFOTO%3C/text%3E%3C/svg%3E" alt="foto">
        </div>

        <label for="uploadfoto" class="btn">UPLOAD FOTO</label>
        <input type="file" id="uploadfoto" accept="image/*">

        <p><span class="label">Nama</span> : Hafidz Az Fadillah</p>
        <p><span class="label">Kelas</span> : X PGIM 1</p>
        <p><span class="label">Absen</span> : 32</p>
        <p><span class="label">Status</span> : Pelajar</p>
        <p><span class="label">Hobi</span> : bermain game </p>
        <p><span class="label">Minat</span> : belum diketahui </p>

        <hr>
        <div style="text-align:right">
            jangan hubungi saya jika tidak ada perlu
        </div>
    </div>

    <script>
        const inp = document.getElementById('uploadfoto');
        const img = document.getElementById('gambar');

        inp.onchange = function(e) {
            const file = e.target.files[0];
            if(file && file.type.startsWith('image/')) {
                const read = new FileReader();
                read.onload = function(ev) { 
                    img.src = ev.target.result; 
                };
                read.readAsDataURL(file);
            } else { 
                alert('file gambar aja'); 
            }
        };

        img.onerror = function() { 
            img.src = 'data:image/svg+xml,%3Csvg width="120" height="120"%3E%3Crect width="120" height="120" fill="%23999"/%3E%3Ctext x="30" y="65" fill="black"%3EFOTO%3C/text%3E%3C/svg%3E'; 
        };
    </script>
</body>
</html>