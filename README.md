# Layanan Peminjaman Buku Online

### Create Pinjam Buku by Id (POST)

<details>
<summary> Klik untuk ekspand </summary>

<table>
<tr>
    <td> URL </td>
    <td> {{baseURL}}/api/v1/pinjam-buku </td>
</tr>
<tr>
    <td> Method </td>
    <td> POST </td>
</tr>
<tr>
    <td> <b> Header </b></td>
    <td> Authorization : Bearer Token </td>
</tr>
<tr>
    <td> <b> Body </b></td>
    <td>

```json
{
  "nama": "kelompok2",
  "id-buku": "bk01",
  "tgl-peminjaman": "2022-12-12",
  "masa-pinjam": "7 Hari"
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Success </b></td>
    <td>

```json
{
  "code": 201,
  "message": "Data Peminjaman Berhasil diinput",
  "data": {
    "id-buku": "bk01",
    "nama": "kelompok2",
    "tgl-peminjaman": "2022-12-12",
    "masa-pinjam": "7 Hari"
  }
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Conflict </b></td>
    <td>

```json
{
  "code": 409,
  "message": "Buku Telah Dipinjam",
  "data": {
    "value": "kelompok2",
    "property": "nama",
    "location": "body"
  }
}
```

</td>
</tr>

</table>
</details>

### Read Peminjaman by Id (GET)

<details>
<summary> Klik untuk ekspand </summary>

<table>
<tr>
    <td> URL </td>
    <td> {{baseURL}}/api/v1/pinjam-buku?id={id} </td>
</tr>
<tr>
    <td> EXAMPLE </td>
    <td> {{baseURL}}/api/v1/pinjam-buku?id=bk01 </td>
</tr>
<tr>
    <td> Method </td>
    <td> GET </td>
</tr>
<tr>
    <td> <b> Header </b></td>
    <td> Authorization : Bearer Token </td>
</tr>
<tr>
    <td> <b> Query </b></td>
    <td> id=bk01 </td>
</tr>

<tr>
    <td> <b> Respon Success With Query </b></td>
    <td>

```json
{
  "code": 200,
  "message": "Data berhasil didapatkan",
  "data": {
    "nama": "kelompok2",
    "tgl-peminjaman": "2022-12-12",
    "masa-pinjam": "7 Hari"
  }
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Not Found </b></td>
    <td>

```json
{
  "code": 404,
  "message": "ID Buku tidak ditemukan",
  "data": {
    "value": "bk01",
    "property": "id-buku",
    "location": "query"
  }
}
```

</td>
</tr>
</table>
</details>

### Update Nama Peminjam Buku (PUT)

<details>
<summary> Klik untuk ekspand </summary>

<table>
<tr>
    <td> URL </td>
    <td> {{baseURL}}/api/v1/pinjam-buku </td>
</tr>
<tr>
    <td> Method </td>
    <td> PUT </td>
</tr>
<tr>
    <td> <b> Header </b></td>
    <td> Authorization : Bearer Token </td>
</tr>
<tr>
    <td> <b> Body </b></td>
    <td>

```json
{
  "id-buku": "bk01",
  "nama": "kelompok3",
  "tgl-peminjaman": "2022-12-12",
  "masa-pinjam": "7 Hari"
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Success </b></td>
    <td>

```json
{
  "code": 201,
  "message": "Data Nama Peminjam Berhasil diubah",
  "data": {
    "id": 1234,
    "nama": "kelompok3",
    "tgl-peminjaman": "2022-12-12",
    "masa-pinjam": "7 Hari"
  }
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Conflict </b></td>
    <td>

```json
{
  "code": 409,
  "message": "Nama Peminjam Telah digunakan",
  "data": {
    "value": "kelompok3",
    "property": "nama",
    "location": "body"
  }
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Not Found </b></td>
    <td>

```json
{
  "code": 404,
  "message": "ID Buku tidak ditemukan",
  "data": {
    "value": "bk01",
    "property": "id-buku",
    "location": "body"
  }
}
```

</td>
</tr>

</table>
</details>

### Delete Peminjaman Buku (DELETE)

<details>
<summary> Klik untuk ekspand </summary>

<table>
<tr>
    <td> URL </td>
    <td> {{baseURL}}/api/v1/pinjam-buku?id={id} </td>
</tr>
<tr>
    <td> EXAMPLE </td>
    <td> {{baseURL}}/api/v1/pinjam-buku?id=bk01 </td>
</tr>
<tr>
    <td> Method </td>
    <td> DELETE </td>
</tr>
<tr>
    <td> <b> Header </b></td>
    <td> Authorization : Bearer Token </td>
</tr>
<tr>
    <td> <b> Query </b></td>
    <td> id=bk01 </td>
</tr>

<tr>
    <td> <b> Respon Success</b></td>
    <td>

```json
{
  "code": 200,
  "message": "Data Peminjaman Buku Berhasil dihapus",
  "data": []
}
```

</td>
</tr>

<tr>
    <td> <b> Respon Not Found </b></td>
    <td>

```json
{
  "code": 404,
  "message": "ID Buku tidak ditemukan",
  "data": {
    "value": "bk01",
    "property": "id-buku",
    "location": "query"
  }
}
```

</td>
</tr>
</table>
</details>
