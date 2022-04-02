<script context="module">
	export const prerender = true;
</script>

<script>
	import Counter from '$lib/Counter.svelte';
	
	import VirtualList from '@sveltejs/svelte-virtual-list';


	const submission = [
    {
        "timestamp": "2022-03-24T10:10:09.082Z",
        "id": 1,
        "fullname": "Olabode Joel Olutoye",
        "portfolioimage": "https://drive.google.com/uc?id=1DpG5QUNq3TTxGwm_ucp-nISlhR5okavh"
    },
    {
        "timestamp": "2022-03-24T10:14:58.211Z",
        "id": 2,
        "fullname": "OBASAN DAUDA TEMITOPE",
        "portfolioimage": "https://drive.google.com/uc?id=135qrHGNkBSY5tOcbpIKuUD0W_ia-9TaL"
    },
    {
        "timestamp": "2022-03-24T10:24:17.913Z",
        "id": 3,
        "fullname": "Blessing Ogar",
        "portfolioimage": "https://drive.google.com/uc?id=16fTkLzf7HQERm6oO82J1gWGICMht88oa"
    },
    {
        "timestamp": "2022-03-24T10:50:13.669Z",
        "id": 4,
        "fullname": "Udeh Ifeanyichukwu",
        "portfolioimage": "https://drive.google.com/uc?id=1HvXR1y2MY_nYNKv2rsX24Lt3V-62TAY9"
    },
    {
        "timestamp": "2022-03-24T11:41:32.031Z",
        "id": 5,
        "fullname": "John Saviour",
        "portfolioimage": "https://drive.google.com/uc?id=1ks_VJQQGcNV6ruLig9aJVYkx1_vPcdUV"
    },
    {
        "timestamp": "2022-03-24T12:33:21.078Z",
        "id": 6,
        "fullname": "Ayomide Gidigbi",
        "portfolioimage": "https://drive.google.com/uc?id=1NjR-ezyNSCZ4b5x8XM-KRVuBWwtaZkAa"
    },
    {
        "timestamp": "2022-03-24T12:34:49.734Z",
        "id": 7,
        "fullname": "Oluwakeji Onabajo",
        "portfolioimage": "https://drive.google.com/uc?id=1MTrcGIN-EB0JIQLQCtJyW5ARwoUAoAsy"
    },
    {
        "timestamp": "2022-03-24T12:36:08.913Z",
        "id": 8,
        "fullname": "Israel Adekanye",
        "portfolioimage": "https://drive.google.com/uc?id=1ETx1PIikeTWcUW5wzb7Gt2bZMDSw_FLU"
    },
    {
        "timestamp": "2022-03-24T12:37:28.894Z",
        "id": 9,
        "fullname": "olutosoye paul",
        "portfolioimage": "https://drive.google.com/uc?id=1lE4KSfr_AJ4XvoCT-CnDz7PfHzIoCr0l"
    },
    {
        "timestamp": "2022-03-24T12:42:04.459Z",
        "id": 10,
        "fullname": "Ajayi Ayomide",
        "portfolioimage": "https://drive.google.com/uc?id=1CqbfjQHZGCS1GhSIV18Ug2bwNkUc84ER"
    },
    {
        "timestamp": "2022-03-24T12:54:53.968Z",
        "id": 11,
        "fullname": "Adekolejo Michael",
        "portfolioimage": "https://drive.google.com/uc?id=1p6ItDtwTXN6tHOdIa6uMGRS15wYXM4Qp"
    },
    {
        "timestamp": "2022-03-24T13:18:09.535Z",
        "id": 12,
        "fullname": "Jimoh Kadiri Bola",
        "portfolioimage": "https://drive.google.com/uc?id=12gymjjxgc24wzP3-bqUOp4brGxzoTB1Y"
    },
    {
        "timestamp": "2022-03-24T13:24:00.635Z",
        "id": 13,
        "fullname": "Lawal Adunola",
        "portfolioimage": "https://drive.google.com/uc?id=1XbH3xwybVW3NZIiwCoxb04TWhmPHasyx"
    },
    {
        "timestamp": "2022-03-24T13:26:43.012Z",
        "id": 14,
        "fullname": "Nzubechukwu Okwuoha",
        "portfolioimage": "https://drive.google.com/uc?id=1K7iO83ZEnfcKJwUgNWkL15h_Viekw4vp"
    },
    {
        "timestamp": "2022-03-24T13:30:49.301Z",
        "id": 15,
        "fullname": "ogunsanu christianah Anu",
        "portfolioimage": "https://drive.google.com/uc?id=13bMz9Iz8SQdIaEByPlo8sEkh8EcjWeVt"
    },
    {
        "timestamp": "2022-03-24T13:37:54.302Z",
        "id": 16,
        "fullname": "Alonge Oluwatobiloba ",
        "portfolioimage": "https://drive.google.com/uc?id=1fx0BC2K-SQCCwAu6Z04c8S7j0YX07O_p"
    },
    {
        "timestamp": "2022-03-24T14:14:11.533Z",
        "id": 17,
        "fullname": "ONI ABAYOMI OLAYIWOLA",
        "portfolioimage": "https://drive.google.com/uc?id=14uyIFpDRmduxm4fBv4q8VlrJw4GlUnhO"
    },
    {
        "timestamp": "2022-03-24T14:23:16.108Z",
        "id": 18,
        "fullname": "Olawale Adeola",
        "portfolioimage": "https://drive.google.com/uc?id=1-xUSjWvVkoF9b4CIEO0sx_qHB-knQG5e"
    },
    {
        "timestamp": "2022-03-24T14:59:00.686Z",
        "id": 19,
        "fullname": "Khadijah Abolanle Thany-Bello",
        "portfolioimage": "https://drive.google.com/uc?id=1EGu_jNXmsrEshzp9gF8_BXppnPu8uWSb"
    },
    {
        "timestamp": "2022-03-24T15:03:16.048Z",
        "id": 20,
        "fullname": "Modupe Ariyo",
        "portfolioimage": "https://drive.google.com/uc?id=1gerPzeE982OHH_cV4GAMXmH2jKqxF3Pl"
    },
    {
        "timestamp": "2022-03-24T15:33:32.847Z",
        "id": 21,
        "fullname": "Adewusi-Lawal",
        "portfolioimage": "https://drive.google.com/uc?id=16NsitJwSSSNwYeosx_ytUK7JsJpGK9MM"
    },
    {
        "timestamp": "2022-03-24T15:51:41.501Z",
        "id": 22,
        "fullname": "Timothy Omamegbe",
        "portfolioimage": "https://drive.google.com/uc?id=1LjUV9mVKXVkkHSIcQ_mTAdNi_Uv08fAO"
    },
    {
        "timestamp": "2022-03-24T16:36:17.859Z",
        "id": 23,
        "fullname": "Ibukun Akinbami",
        "portfolioimage": "https://drive.google.com/uc?id=13oH8w6Dnuxf8Ba5e9jac11hLKL1R4-Or"
    },
    {
        "timestamp": "2022-03-24T19:37:56.672Z",
        "id": 24,
        "fullname": "Emmanuel Osas Ogbokhun",
        "portfolioimage": "https://drive.google.com/uc?id=1Gpo_eoGknsbdNhRocQtPkICa-ibNHMtL"
    },
    {
        "timestamp": "2022-03-24T21:51:18.018Z",
        "id": 25,
        "fullname": "ADEROGBA OLUWASEYIFUNMI",
        "portfolioimage": "https://drive.google.com/uc?id=1RgtHkCPiqle-lmbyDJ6ITbfBRQHt9pxN"
    },
    {
        "timestamp": "2022-03-26T11:47:10.572Z",
        "id": 26,
        "fullname": "Oguntade Adebola Aliu",
        "portfolioimage": "https://drive.google.com/uc?id=1ocON7GK0wE3VjZq5xOGAl7dpDzithgmG"
    },
    {
        "timestamp": "2022-03-27T17:21:25.398Z",
        "id": 27,
        "fullname": "Babajide ",
        "portfolioimage": "https://drive.google.com/uc?id=1fjoEmK72dWdiQHf1qolSu3tLYIEA_7Nd"
    },
    {
        "timestamp": "2022-03-28T06:46:50.053Z",
        "id": 28,
        "fullname": "Abiodun Aderibigbe",
        "portfolioimage": "https://drive.google.com/uc?id=1j3B5YK2oKI97x6r90UxFpsU4ZLEzykHB"
    },
    {
        "timestamp": "2022-03-28T10:35:19.577Z",
        "id": 29,
        "fullname": "Rapheal Ogunnaike",
        "portfolioimage": "https://drive.google.com/uc?id=1AB9YygsmJX_41pxY-dqzxwqAZP9zIhAL"
    },
    {
        "timestamp": "2022-03-28T13:25:10.110Z",
        "id": 30,
        "fullname": "Babajide Aroyewun ",
        "portfolioimage": "https://drive.google.com/uc?id=1m8ST4KoZXPSM3qIi-ngD3B3P1FlQPjpw"
    }
];
	
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	

	<h3>
		SAIL x Findworka Portfolio Submission Data Page
	</h3>
	
<VirtualList height="500px" items={submission} let:item>
	<div class="flex-container">
		<div class="numbering">
			<span>{item.id}</span>
		</div>
		<div class="candidateName">
			<span>{item.fullname}</span>
		</div>
		<div class="candidatePortfolioPreview">
			<a target="_blank" href={item.portfolioimage}><img width="50px" height="50px" src={item.portfolioimage} alt=""></a>
		</div>
	</div>

	<br>
</VirtualList>
</section>

<style>
	.numbering {
		padding-top: 15px;
		margin-right: 10px;
	}
	.candidateName{
		/* background-color: rgb(179, 193, 195); */
		padding-top: 15px;
		width: 250px;

	}
	.candidatePortfolioPreview{
		/* background-color: rgb(179, 193, 195); */
		padding-top: auto;
		padding-bottom: auto;
	}
	.flex-container {
		display: flex;
		width: 100%;
		overflow: hidden;
	}

	.flex-container:hover {
		background-color: rgb(89, 99, 100);
		color: aliceblue;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}
	h3 {
		text-align: center;
	}
</style>
