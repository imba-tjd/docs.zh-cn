### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="0d212-101">SqlConnection 可以不再连接到 SQL Server 1997 或使用 VIA 适配器的数据库</span><span class="sxs-lookup"><span data-stu-id="0d212-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0d212-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d212-102">Details</span></span>|<span data-ttu-id="0d212-103">不再支持使用[虚拟接口适配器 (VIA) 协议](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx)连接到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="0d212-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx) are no longer supported.</span></span> <span data-ttu-id="0d212-104">连接字符串中可以见到用于连接到 SQL Server 数据库的协议。</span><span class="sxs-lookup"><span data-stu-id="0d212-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="0d212-105">VIA 连接将包含 via:&lt;servername&gt;。</span><span class="sxs-lookup"><span data-stu-id="0d212-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="0d212-106">如果此应用通过协议而不是 VIA （例如 tcp: 或 np:）连接到 SQL，则不会遇到中断的更改。此外，也不再支持连接到 SQL Server 7 (1997)。</span><span class="sxs-lookup"><span data-stu-id="0d212-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>|
|<span data-ttu-id="0d212-107">建议</span><span class="sxs-lookup"><span data-stu-id="0d212-107">Suggestion</span></span>|<span data-ttu-id="0d212-108">VIA 协议已弃用，因此，应使用备用协议连接到 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="0d212-108">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="0d212-109">使用的最常见的协议是 TCP/IP。</span><span class="sxs-lookup"><span data-stu-id="0d212-109">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="0d212-110">在[此处](https://msdn.microsoft.com/library/bb909712.aspx)可以找到有关启用 TCP/IP 协议的说明。</span><span class="sxs-lookup"><span data-stu-id="0d212-110">Instructions for enabling the TCP/IP protocol can be found [here](https://msdn.microsoft.com/library/bb909712.aspx).</span></span> <span data-ttu-id="0d212-111">如果只能从 Intranet 访问数据库，在网络速度慢时，共享的管道协议可能会提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="0d212-111">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>|
|<span data-ttu-id="0d212-112">范围</span><span class="sxs-lookup"><span data-stu-id="0d212-112">Scope</span></span>|<span data-ttu-id="0d212-113">边缘</span><span class="sxs-lookup"><span data-stu-id="0d212-113">Edge</span></span>|
|<span data-ttu-id="0d212-114">版本</span><span class="sxs-lookup"><span data-stu-id="0d212-114">Version</span></span>|<span data-ttu-id="0d212-115">4.5</span><span class="sxs-lookup"><span data-stu-id="0d212-115">4.5</span></span>|
|<span data-ttu-id="0d212-116">类型</span><span class="sxs-lookup"><span data-stu-id="0d212-116">Type</span></span>|<span data-ttu-id="0d212-117">运行时</span><span class="sxs-lookup"><span data-stu-id="0d212-117">Runtime</span></span>|
|<span data-ttu-id="0d212-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="0d212-118">Affected APIs</span></span>|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|
