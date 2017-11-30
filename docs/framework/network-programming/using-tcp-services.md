---
title: TCP Hizmetleri kullanma
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f560ae08c928e9f21def9f69950efbd72ccb6b88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-tcp-services"></a><span data-ttu-id="037af-102">TCP Hizmetleri kullanma</span><span class="sxs-lookup"><span data-stu-id="037af-102">Using TCP Services</span></span>
<span data-ttu-id="037af-103"><xref:System.Net.Sockets.TcpClient> Sınıfı TCP kullanarak bir Internet kaynağından veri ister.</span><span class="sxs-lookup"><span data-stu-id="037af-103">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="037af-104">Özellikleri ve yöntemleri **TcpClient** oluşturmak için ayrıntıları soyut bir <xref:System.Net.Sockets.Socket> isteme ve TCP kullanarak veri almak için.</span><span class="sxs-lookup"><span data-stu-id="037af-104">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="037af-105">Uzak aygıt bağlantısı bir akış olarak temsil edilir çünkü veri okumak ve .NET Framework akış işleme teknikleri ile yazılır.</span><span class="sxs-lookup"><span data-stu-id="037af-105">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>  
  
 <span data-ttu-id="037af-106">TCP protokolü uzak uç noktasıyla bağlantı kurar ve veri paket göndermek ve almak için bu bağlantıyı kullanır.</span><span class="sxs-lookup"><span data-stu-id="037af-106">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="037af-107">TCP veri paketlerinin uç noktasına gönderilen ve doğru sırada geldiğinde birleştirilen emin sorumludur.</span><span class="sxs-lookup"><span data-stu-id="037af-107">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>  
  
 <span data-ttu-id="037af-108">TCP bağlantı kurmak için gereksinim duyduğunuz hizmetini barındıran ağ aygıtı adresini bilmeniz gerekir ve hizmetin iletişim kurmak için kullandığı TCP bağlantı noktasını bilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="037af-108">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="037af-109">Internet Atanmış Numaralar Yetkilisi (IANA) (www.iana.org/assignments/port-numbers bakın) ortak Hizmetleri için bağlantı noktası numaralarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="037af-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="037af-110">IANA listede olmayan Hizmetleri bağlantı noktası numaraları 1024 65. 535'ı için aralığında olabilir.</span><span class="sxs-lookup"><span data-stu-id="037af-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="037af-111">Aşağıdaki örnek, Yukarı ayarını gösterir. bir **TcpClient** numaralı TCP bağlantı noktasında 13 zaman sunucuya bağlanılamadı.</span><span class="sxs-lookup"><span data-stu-id="037af-111">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13.</span></span>  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeClient  
    Private const portNum As Integer = 13  
    Private const hostName As String = "host.contoso.com"  
  
    ' Entry point  that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Try  
            Dim client As New TcpClient(hostName, portNum)  
  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim bytes(1024) As Byte  
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))  
  
        Catch e As Exception  
            Console.WriteLine(e.ToString())  
        End Try  
  
        client.Close()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeClient  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <span data-ttu-id="037af-112"><xref:System.Net.Sockets.TcpListener>bir TCP bağlantı noktası gelen istekler için izleme ve ya da oluşturmak için kullanılan bir **yuva** veya **TcpClient** istemciye bağlantıyı yönetir.</span><span class="sxs-lookup"><span data-stu-id="037af-112"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="037af-113"><xref:System.Net.Sockets.TcpListener.Start%2A> Yöntemi etkinleştirir dinleme ve <xref:System.Net.Sockets.TcpListener.Stop%2A> yöntemi bağlantı noktası üzerinde dinleme devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="037af-113">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="037af-114"><xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> Yöntemi gelen bağlantı isteklerini kabul eder ve oluşturur bir **TcpClient** isteği işlemek üzere ve <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> yöntemi gelen bağlantı isteklerini kabul eder ve oluşturur bir **yuva**isteği işlemek üzere.</span><span class="sxs-lookup"><span data-stu-id="037af-114">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>  
  
 <span data-ttu-id="037af-115">Aşağıdaki örnek, bir ağ zaman sunucu kullanarak oluşturma gösterir bir **TcpListener** TCP bağlantı noktası 13 izlemek için.</span><span class="sxs-lookup"><span data-stu-id="037af-115">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="037af-116">Gelen bir bağlantı isteği kabul edildiğinde zaman sunucu geçerli tarih ve saat konak sunucusundan yanıt verir.</span><span class="sxs-lookup"><span data-stu-id="037af-116">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
        listener.Start()  
  
        While Not done  
            Console.Write("Waiting for connection...")  
            Dim client As TcpClient = listener.AcceptTcpClient()  
  
            Console.WriteLine("Connection accepted.")  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim byteTime As Byte() = _  
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())  
  
            Try  
                ns.Write(byteTime, 0, byteTime.Length)  
                ns.Close()  
                client.Close()  
            Catch e As Exception  
                Console.WriteLine(e.ToString())  
            End Try  
        End While  
  
        listener.Stop()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="037af-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="037af-117">See Also</span></span>  
 