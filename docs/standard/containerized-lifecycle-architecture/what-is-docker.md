---
title: "O que é o Docker?"
description: "Ciclo de vida de aplicativo de Docker em contêineres com ferramentas e plataformas da Microsoft"
keywords: "Docker, Microsserviços, ASP.NET, Contêiner"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 7b429f84f7714454d49be1cfa4f450d99fc47f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="what-is-docker"></a><span data-ttu-id="1352a-104">O que é o Docker?</span><span class="sxs-lookup"><span data-stu-id="1352a-104">What is Docker?</span></span>

<span data-ttu-id="1352a-105">[Docker](https://www.docker.com/) é um [projeto de código-fonte aberto](https://github.com/docker/docker) para automatizar a implantação de aplicativos como contêineres auto-suficiente, portáteis que podem ser executados na nuvem ou local (consulte a Figura 1 e 2).</span><span class="sxs-lookup"><span data-stu-id="1352a-105">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run in the cloud or on-premises (see Figure 1-2).</span></span> <span data-ttu-id="1352a-106">A docker é também um [empresa](https://www.docker.com/) que promove e desenvolve essa tecnologia, trabalhar em colaboração com a nuvem, Linux e fornecedores do Windows, incluindo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1352a-106">Docker is also a [company](https://www.docker.com/) that promotes and develops this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![](./media/image2.png)

<span data-ttu-id="1352a-107">Figura 1-2-Docker implanta contêineres em todas as camadas da nuvem híbrida</span><span class="sxs-lookup"><span data-stu-id="1352a-107">Figure 1-2: Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="1352a-108">Contêineres de imagem do docker podem executar nativamente no Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="1352a-108">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="1352a-109">No entanto, imagens do Windows podem executar somente em hosts do Windows e Linux imagens podem executar somente em hosts Linux, que significa que um servidor de host ou em uma VM.</span><span class="sxs-lookup"><span data-stu-id="1352a-109">However, Windows images can run only on Windows hosts and Linux images can run only on Linux hosts, meaning a host server or a VM.</span></span>

<span data-ttu-id="1352a-110">Os desenvolvedores podem usar os ambientes de desenvolvimento no Windows, Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="1352a-110">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="1352a-111">No computador de desenvolvimento, o desenvolvedor executa um host Docker para qual Docker imagens forem implantadas, incluindo o aplicativo e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="1352a-111">On the development computer, the developer runs a Docker host to which Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="1352a-112">Os desenvolvedores que trabalham no Linux ou no Mac usam um host Docker é baseado em Linux, e podem criar imagens apenas para contêineres do Linux.</span><span class="sxs-lookup"><span data-stu-id="1352a-112">Developers who work on Linux or on the Mac use a Docker host that is Linux based, and they can create images only for Linux containers.</span></span> <span data-ttu-id="1352a-113">(Os desenvolvedores que trabalham no Mac podem editar o código ou executar a interface de linha de comando do Docker \[CLI\] de macOS, mas, redação deste artigo, os contêineres não executados diretamente em macOS.) Os desenvolvedores que trabalham no Windows podem criar imagens de contêineres do Windows ou Linux.</span><span class="sxs-lookup"><span data-stu-id="1352a-113">(Developers working on the Mac can edit code or run the Docker command-line interface \[CLI\] from macOS, but, as of this writing, containers do not run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="1352a-114">Para hospedar os contêineres em ambientes de desenvolvimento e fornecem ferramentas de desenvolvedor adicionais, vem Docker [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows ou macOS.</span><span class="sxs-lookup"><span data-stu-id="1352a-114">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="1352a-115">Esses produtos instalam o VM necessário (o host do Docker) para hospedar os contêineres.</span><span class="sxs-lookup"><span data-stu-id="1352a-115">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="1352a-116">Docker também disponibiliza [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), que é projetado para desenvolvimento empresarial e é usado por equipes de TI que criam, enviar e executar aplicativos essenciais aos negócios grandes em produção.</span><span class="sxs-lookup"><span data-stu-id="1352a-116">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="1352a-117">Para executar [contêineres do Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), há dois tipos de tempos de execução:</span><span class="sxs-lookup"><span data-stu-id="1352a-117">To run [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), there are two types of runtimes:</span></span>

-   <span data-ttu-id="1352a-118">**Contêiner do Windows Server** esse tempo de execução fornece isolamento de aplicativos por meio da tecnologia de isolamento de processo e de namespace.</span><span class="sxs-lookup"><span data-stu-id="1352a-118">**Windows Server Container** This runtime provides application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="1352a-119">Um contêiner do Windows Server compartilha um kernel com o host do contêiner e todos os contêineres em execução no host.</span><span class="sxs-lookup"><span data-stu-id="1352a-119">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

-   <span data-ttu-id="1352a-120">**Contêiner do Hyper-V** isso expande o isolamento fornecido pelos contêineres do Windows Server, executando cada contêiner em uma máquina virtual altamente otimizada.</span><span class="sxs-lookup"><span data-stu-id="1352a-120">**Hyper-V Container** This expands on the isolation provided by Windows Server Containers by running each container in a highly optimized VM.</span></span> <span data-ttu-id="1352a-121">Nessa configuração, o kernel do host do contêiner não é compartilhado com os contêineres do Hyper-V, fornece melhor isolamento.</span><span class="sxs-lookup"><span data-stu-id="1352a-121">In this configuration, the kernel of the container host is not shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="1352a-122">As imagens para esses contêineres são criadas da mesma forma e funcionam da mesma.</span><span class="sxs-lookup"><span data-stu-id="1352a-122">The images for these containers are created in the same way and function the same.</span></span> <span data-ttu-id="1352a-123">A diferença é como o contêiner é criado por meio da imagem, a execução de um contêiner do Hyper-V exige um parâmetro extra.</span><span class="sxs-lookup"><span data-stu-id="1352a-123">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="1352a-124">Para obter detalhes, consulte [contêineres do Hyper-V](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).</span><span class="sxs-lookup"><span data-stu-id="1352a-124">For details, see [Hyper-V Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).</span></span>

## <a name="comparing-docker-containers-with-vms"></a><span data-ttu-id="1352a-125">Comparando os contêineres do Docker com máquinas virtuais</span><span class="sxs-lookup"><span data-stu-id="1352a-125">Comparing Docker containers with VMs</span></span>

<span data-ttu-id="1352a-126">Figura 1-3 mostra uma comparação entre VMs e Docker contêineres.</span><span class="sxs-lookup"><span data-stu-id="1352a-126">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

<span data-ttu-id="1352a-127">Como contêineres exigem muito menos recursos (por exemplo, eles não é necessário um SO completo), são fáceis de implantar e começar rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1352a-127">Because containers require far fewer resources (for example, they do not need a full OS), they are easy to deploy and they start fast.</span></span> <span data-ttu-id="1352a-128">Isso possibilita que você tenha a densidade mais alta, o que significa que você pode executar mais serviços na mesma unidade de hardware, reduzindo os custos.</span><span class="sxs-lookup"><span data-stu-id="1352a-128">This makes it possible for you to have higher density, meaning that you can run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="1352a-129">Como um efeito colateral da execução no mesmo kernel, você obtém menos isolamento de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="1352a-129">As a side effect of running on the same kernel, you achieve less isolation than VMs.</span></span>

<span data-ttu-id="1352a-130">O objetivo principal de uma imagem é que ele faz o ambiente (dependências) os mesmos entre diferentes implantações.</span><span class="sxs-lookup"><span data-stu-id="1352a-130">The main goal of an image is that it makes the environment (dependencies) the same across different deployments.</span></span> <span data-ttu-id="1352a-131">Isso significa que você pode depurá-lo em seu computador e, em seguida, implantá-lo para outro computador com o mesmo ambiente de garantia.</span><span class="sxs-lookup"><span data-stu-id="1352a-131">This means that you can debug it on your machine and then deploy it to another machine with the same environment guaranteed.</span></span>

<span data-ttu-id="1352a-132">Uma imagem de contêiner é uma maneira para empacotar um aplicativo ou serviço e implantá-lo de uma maneira confiável e reproduzível.</span><span class="sxs-lookup"><span data-stu-id="1352a-132">A container image is a way to package an app or service and deploy it in a reliable and reproducible manner.</span></span> <span data-ttu-id="1352a-133">Nesse sentido, o Docker não é apenas uma tecnologia, também é uma filosofia e um processo.</span><span class="sxs-lookup"><span data-stu-id="1352a-133">In this respect, Docker is not only a technology, it's also a philosophy and a process.</span></span>

<span data-ttu-id="1352a-134">Ao usar o Docker, você não verá os desenvolvedores dizer, "Funciona no meu computador, por que não em produção?"</span><span class="sxs-lookup"><span data-stu-id="1352a-134">When using Docker, you will not hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="1352a-135">Pode simplesmente dizem, "Executa no Docker," porque o aplicativo empacotado do Docker pode ser executado em qualquer ambiente de Docker, e ela será executada da maneira que ele estivesse destinado a em todos os destinos de implantação (desenvolvimento, QA, preparo, produção, etc.).</span><span class="sxs-lookup"><span data-stu-id="1352a-135">They can simply say, "It runs on Docker," because the packaged Docker application can be run on any supported Docker environment, and it will run the way it was intended to on all deployment destinations (Dev, QA, staging, production, etc.).</span></span>

![](./media/image3.png)

<span data-ttu-id="1352a-136">Figura 1-3: comparação das VMs tradicionais para contêineres do Docker</span><span class="sxs-lookup"><span data-stu-id="1352a-136">Figure 1-3: Comparison of traditional VMs to Docker containers</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1352a-137">[Anterior] (index.md) [Avançar] (docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="1352a-137">[Previous] (index.md) [Next] (docker-terminology.md)</span></span>