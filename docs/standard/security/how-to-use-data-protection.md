---
title: "Como usar proteção de dados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 99608c991d79d204085f190c00e347aae15eb2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="84e40-102">Como usar proteção de dados</span><span class="sxs-lookup"><span data-stu-id="84e40-102">How to: Use Data Protection</span></span>
<span data-ttu-id="84e40-103">O .NET Framework fornece acesso para a proteção de dados DPAPI (API), que permite que você criptografe os dados usando as informações da conta de usuário atual ou computador.</span><span class="sxs-lookup"><span data-stu-id="84e40-103">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="84e40-104">Quando você usar a DPAPI, você aliviar o problema difícil de explicitamente gerar e armazenar uma chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="84e40-104">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="84e40-105">Use o <xref:System.Security.Cryptography.ProtectedMemory> classe para criptografar uma matriz de bytes de memória.</span><span class="sxs-lookup"><span data-stu-id="84e40-105">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="84e40-106">Essa funcionalidade está disponível no Microsoft Windows XP e sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="84e40-106">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="84e40-107">Você pode especificar que a memória criptografada pelo atual processo pode ser descriptografado pelo processo atual, por todos os processos ou o mesmo contexto de usuário.</span><span class="sxs-lookup"><span data-stu-id="84e40-107">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="84e40-108">Consulte o <xref:System.Security.Cryptography.MemoryProtectionScope> enumeração para uma descrição detalhada do <xref:System.Security.Cryptography.ProtectedMemory> opções.</span><span class="sxs-lookup"><span data-stu-id="84e40-108">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="84e40-109">Use o <xref:System.Security.Cryptography.ProtectedData> classe para criptografar uma cópia de uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="84e40-109">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="84e40-110">Essa funcionalidade está disponível no Microsoft Windows 2000 e sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="84e40-110">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="84e40-111">Você pode especificar que os dados criptografados pela conta do usuário atual podem ser descriptografados apenas pela mesma conta de usuário, ou você pode especificar que os dados criptografados pela conta do usuário atual podem ser descriptografados por qualquer conta no computador.</span><span class="sxs-lookup"><span data-stu-id="84e40-111">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="84e40-112">Consulte o <xref:System.Security.Cryptography.DataProtectionScope> enumeração para uma descrição detalhada do <xref:System.Security.Cryptography.ProtectedData> opções.</span><span class="sxs-lookup"><span data-stu-id="84e40-112">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="84e40-113">Para criptografar dados na memória usando a proteção de dados</span><span class="sxs-lookup"><span data-stu-id="84e40-113">To encrypt in-memory data using data protection</span></span>  
  
1.  <span data-ttu-id="84e40-114">Chamar estático <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> método passando uma matriz de bytes para criptografar a entropia e o escopo de proteção de memória.</span><span class="sxs-lookup"><span data-stu-id="84e40-114">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="84e40-115">Para descriptografar os dados na memória usando a proteção de dados</span><span class="sxs-lookup"><span data-stu-id="84e40-115">To decrypt in-memory data using data protection</span></span>  
  
1.  <span data-ttu-id="84e40-116">Chamar estático <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> método passando uma matriz de bytes para descriptografar e o escopo de proteção de memória.</span><span class="sxs-lookup"><span data-stu-id="84e40-116">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="84e40-117">Para criptografar dados em um arquivo ou fluxo usando proteção de dados</span><span class="sxs-lookup"><span data-stu-id="84e40-117">To encrypt data to a file or stream using data protection</span></span>  
  
1.  <span data-ttu-id="84e40-118">Crie entropia aleatória.</span><span class="sxs-lookup"><span data-stu-id="84e40-118">Create random entropy.</span></span>  
  
2.  <span data-ttu-id="84e40-119">Chamar estático <xref:System.Security.Cryptography.ProtectedData.Protect%2A> método passando uma matriz de bytes para criptografar a entropia e o escopo de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="84e40-119">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3.  <span data-ttu-id="84e40-120">Grave os dados criptografados em um arquivo ou fluxo.</span><span class="sxs-lookup"><span data-stu-id="84e40-120">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="84e40-121">Para descriptografar os dados de um arquivo ou fluxo usando proteção de dados</span><span class="sxs-lookup"><span data-stu-id="84e40-121">To decrypt data from a file or stream using data protection</span></span>  
  
1.  <span data-ttu-id="84e40-122">Ler os dados criptografados em um arquivo ou fluxo.</span><span class="sxs-lookup"><span data-stu-id="84e40-122">Read the encrypted data from a file or stream.</span></span>  
  
2.  <span data-ttu-id="84e40-123">Chamar estático <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> método passando uma matriz de bytes para descriptografar e o escopo de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="84e40-123">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e40-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="84e40-124">Example</span></span>  
 <span data-ttu-id="84e40-125">O exemplo de código a seguir demonstra duas formas de criptografia e descriptografia.</span><span class="sxs-lookup"><span data-stu-id="84e40-125">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="84e40-126">Primeiro, o exemplo de código criptografa e descriptografa uma matriz de memória de bytes.</span><span class="sxs-lookup"><span data-stu-id="84e40-126">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="84e40-127">Em seguida, o exemplo de código criptografa uma cópia de uma matriz de bytes, salva-o em um arquivo, carrega os dados do arquivo e descriptografa os dados.</span><span class="sxs-lookup"><span data-stu-id="84e40-127">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="84e40-128">O exemplo exibe os dados originais, os dados criptografados e os dados descriptografados.</span><span class="sxs-lookup"><span data-stu-id="84e40-128">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84e40-129">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="84e40-129">Compiling the Code</span></span>  
  
-   <span data-ttu-id="84e40-130">Incluir uma referência a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="84e40-130">Include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="84e40-131">Incluir o <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, e <xref:System.Text> namespace.</span><span class="sxs-lookup"><span data-stu-id="84e40-131">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e40-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="84e40-132">See Also</span></span>  
 <xref:System.Security.Cryptography.ProtectedMemory>  
 <xref:System.Security.Cryptography.ProtectedData>