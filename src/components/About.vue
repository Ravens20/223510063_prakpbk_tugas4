<template>
    <div class="about">
      <div class="text">
        <img src="../image/profile.png" alt="Dindra Desvantio" class="profile-pic"/>
        <h1>Tentang Dindra Desvantio</h1>
        <div class="paragraphs">
          <div class="left">
            <div class="paragraph">
              <h2>Kuliah di Universitas Islam Riau</h2>
              <p>
                Halo! Nama saya Dindra Desvantio. Saya saat ini adalah mahasiswa di Universitas Islam Riau, 
                jurusan Teknik Informatika di Fakultas Teknik. Saya memiliki minat yang besar terhadap teknologi 
                dan senang belajar tentang perkembangan terbaru di bidang ini.
              </p>
            </div>
            <div class="paragraph">
              <h2>Pengalaman Akademis</h2>
              <p>
                Selama studi, saya telah menguasai berbagai bahasa pemrograman termasuk JavaScript, 
                Python, dan C++. Saya juga mengembangkan keterampilan dalam pengembangan web, struktur data, algoritma, 
                dan rekayasa perangkat lunak.
              </p>
            </div>
          </div>
          <div class="right">
            <div class="paragraph">
              <h2>Kegiatan Ekstrakurikuler</h2>
              <p>
                Di luar kegiatan akademis, saya aktif terlibat dalam beberapa kegiatan ekstrakurikuler. 
                Saya adalah anggota klub teknologi di universitas di mana kami mengorganisir lokakarya dan hackathon untuk mempromosikan 
                teknologi dan inovasi.
              </p>
            </div>
            <div class="paragraph">
              <h2>Tujuan di Masa Depan</h2>
              <p>
                Tujuan saya adalah menjadi seorang insinyur perangkat lunak yang handal dan berkontribusi dalam proyek-proyek inovatif 
                yang dapat memberikan dampak positif bagi masyarakat. Saya sangat tertarik pada bidang seperti kecerdasan buatan, 
                pembelajaran mesin, dan pengembangan web.
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="gallery">
        <div class="gallery-item">
          <img src="../image/html.webp" alt="Foto 1" class="gallery-img">
          <div class="overlay"></div>
        </div>
        <div class="gallery-item">
          <img src="../image/vue.png" alt="Foto 2" class="gallery-img">
          <div class="overlay"></div>
        </div>
        <div class="gallery-item">
          <img src="../image/javascript_image.png" alt="Foto 3" class="gallery-img">
          <div class="overlay"></div>
        </div>
      </div>
      <slot></slot>
    </div>
  </template>
  
  <script>
  export default {
  };
  </script>
  
  <style>
  .about {
    padding: 40px;
    max-width: 900px;
    margin: 0 auto;
    background-color: #1c1c1c;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
    line-height: 1.6;
    font-family: 'Helvetica Neue', Arial, sans-serif;
  }
  
  .text {
    margin-bottom: 40px;
  }
  
  .profile-pic {
    border-radius: 50%;
    width: 150px;
    height: 150px;
    object-fit: cover;
    margin: 0 auto 20px;
    display: block;
    border: 5px solid #ffdd57;
  }
  
  .text h1 {
    font-size: 2.5em;
    color: #ffdd57;
    text-align: center;
    margin-bottom: 20px;
    font-weight: 700;
  }
  
  p {
    color: rgba(206, 202, 202, 0.879);
  }

  h2 {
    color: rgba(255, 255, 255, 0.864);
    font-weight: 700;
  }
  
  .paragraphs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  
  .left {
    grid-column: 1 / span 1;
  }
  
  .right {
    grid-column: 2 / span 1;
  }
  
  .paragraph {
    padding: 10px;
    margin: 30px;
    background-color: rgba(0, 0, 0, 0.838);
    border-radius: 8px;
    position: relative;
    transition: transform 0.3s ease;
  }
  
  .paragraph:hover {
    transform: translateY(-5px);
  }
  .paragraph:hover h2{
    color:#ffdd57;
  }
  
  .paragraph::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0);
    transition: background-color 0.3s ease;
    border-radius: 8px;
  }
  
  .paragraph:hover::after {
    background-color: rgba(0, 0, 0, 0.1);
  }
  
  .gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 20px;
}  
.gallery-item {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  transition: transform 0.3s ease;
}  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    opacity: 0;
    transition: opacity 0.3s ease; 
  }
  
  .gallery-item:hover {
  transform: scale(1.05);
}  
.gallery-img {
  width: 100%;
  height: auto;
  object-fit: cover;
}  
  .gallery-item:hover .gallery-img {
    transform: scale(1.05);
  }
  </style>
  