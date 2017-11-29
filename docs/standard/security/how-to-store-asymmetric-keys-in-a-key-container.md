---
title: "Como armazenar chaves assimétricas em um contêiner de chave"
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
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 475139230c4b58bc6dcc307bd99eeafdc3e89e53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="bca5b-102">Como armazenar chaves assimétricas em um contêiner de chave</span><span class="sxs-lookup"><span data-stu-id="bca5b-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="bca5b-103">As chaves privadas assimétricas nunca devem ser armazenadas no formato textual nem como texto sem formatação no computador local.</span><span class="sxs-lookup"><span data-stu-id="bca5b-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="bca5b-104">Se precisar armazenar uma chave privada, você deverá usar um contêiner de chave.</span><span class="sxs-lookup"><span data-stu-id="bca5b-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="bca5b-105">Para obter mais informações sobre contêineres de chave, consulte [Noções básicas sobre nível de máquina e recipientes de chave RSA nível de usuário](http://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span><span class="sxs-lookup"><span data-stu-id="bca5b-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](http://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="bca5b-106">Para criar uma chave assimétrica e salvá-la em um contêiner de chaves</span><span class="sxs-lookup"><span data-stu-id="bca5b-106">To create an asymmetric key and save it in a key container</span></span>  
  
1.  <span data-ttu-id="bca5b-107">Criar uma nova instância de um <xref:System.Security.Cryptography.CspParameters> classe e passe o nome que você deseja chamar o contêiner de chave para o <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="bca5b-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2.  <span data-ttu-id="bca5b-108">Criar uma nova instância de uma classe que deriva de <xref:System.Security.Cryptography.AsymmetricAlgorithm> classe (geralmente **RSACryptoServiceProvider** ou **DSACryptoServiceProvider**) e passar criado anteriormente  **CspParameters** objeto para o construtor.</span><span class="sxs-lookup"><span data-stu-id="bca5b-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="bca5b-109">Para excluir uma chave de um contêiner de chaves</span><span class="sxs-lookup"><span data-stu-id="bca5b-109">To delete the key from a key container</span></span>  
  
1.  <span data-ttu-id="bca5b-110">Criar uma nova instância de um **CspParameters** classe e passe o nome que você deseja chamar o contêiner de chave para o **CspParameters.KeyContainerName** campo.</span><span class="sxs-lookup"><span data-stu-id="bca5b-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2.  <span data-ttu-id="bca5b-111">Criar uma nova instância de uma classe que deriva de **AsymmetricAlgorithm** classe (geralmente **RSACryptoServiceProvider** ou **DSACryptoServiceProvider**) e passar o criado anteriormente **CspParameters** objeto para o construtor.</span><span class="sxs-lookup"><span data-stu-id="bca5b-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3.  <span data-ttu-id="bca5b-112">Definir o **PersistKeyInCSP** propriedade da classe que deriva de **AsymmetricAlgorithm** para **false** (**False** no Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="bca5b-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4.  <span data-ttu-id="bca5b-113">Chamar o **limpar** método da classe que deriva de **AsymmetricAlgorithm**.</span><span class="sxs-lookup"><span data-stu-id="bca5b-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="bca5b-114">Esse método libera todos os recursos da classe e limpa o contêiner de chaves.</span><span class="sxs-lookup"><span data-stu-id="bca5b-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca5b-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bca5b-115">Example</span></span>  
 <span data-ttu-id="bca5b-116">O exemplo a seguir mostra como criar uma chave assimétrica, salvá-la em um contêiner de chaves, recuperar a chave posteriormente e excluir a chave do contêiner.</span><span class="sxs-lookup"><span data-stu-id="bca5b-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="bca5b-117">Observe que o código no `GenKey_SaveInContainer` método e o `GetKeyFromContainer` método é semelhante.</span><span class="sxs-lookup"><span data-stu-id="bca5b-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="bca5b-118">Quando você especifica o nome do contêiner de chaves para um objeto <xref:System.Security.Cryptography.CspParameters> e o informa a um objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> com a propriedade <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> ou <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> definida como true, acontece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bca5b-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="bca5b-119">se o contêiner de chaves com o nome especificado não existir, ele será criado e a chave persistirá.</span><span class="sxs-lookup"><span data-stu-id="bca5b-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="bca5b-120">Se o contêiner de chaves com o nome especificado existir, a chave será carregada automaticamente no objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> atual.</span><span class="sxs-lookup"><span data-stu-id="bca5b-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="bca5b-121">Assim, o método `GenKey_SaveInContainer` persiste na chave porque ele é executado primeiro. Enquanto isso, o código do método `GetKeyFromContainer` carrega a chave porque ele é executado na sequência.</span><span class="sxs-lookup"><span data-stu-id="bca5b-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="bca5b-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bca5b-122">See Also</span></span>  
 [<span data-ttu-id="bca5b-123">Geração de chaves para criptografia e descriptografia</span><span class="sxs-lookup"><span data-stu-id="bca5b-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
 [<span data-ttu-id="bca5b-124">Criptografando dados</span><span class="sxs-lookup"><span data-stu-id="bca5b-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
 [<span data-ttu-id="bca5b-125">Descriptografando dados</span><span class="sxs-lookup"><span data-stu-id="bca5b-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
 [<span data-ttu-id="bca5b-126">Serviços criptográficos</span><span class="sxs-lookup"><span data-stu-id="bca5b-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)