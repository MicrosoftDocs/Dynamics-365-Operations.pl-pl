---
title: Włączanie usługi Power BI dla Globalnego księgowania zapasów
description: W tym temacie opisano sposób włączenia w Microsoft Power BI funkcji Globalnego księgowanie zapasów.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273209"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="59e2b-103">Włączanie usługi Power BI dla Globalnego księgowania zapasów</span><span class="sxs-lookup"><span data-stu-id="59e2b-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="59e2b-104">Kafelki, pulpity nawigacyjne i raporty [PowerBI.com](https://powerbi.com/) można przypiąć do obszaru roboczego aplikacji Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="59e2b-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59e2b-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="59e2b-105">Prerequisites</span></span>

<span data-ttu-id="59e2b-106">Zanim będzie można włączyć raportowanie w Power BI, muszą być spełnione następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="59e2b-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="59e2b-107">Musisz być administratorem systemu w aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="59e2b-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="59e2b-108">Musisz mieć konto [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="59e2b-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="59e2b-109">Musisz mieć przynajmniej jeden pulpit i jeden raport na swoim koncie Power BI.</span><span class="sxs-lookup"><span data-stu-id="59e2b-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="59e2b-110">Musisz być administratorem swojego konta Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="59e2b-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="59e2b-111">Domena Azure AD musi być taką samą domeną, jak używana dla konta [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="59e2b-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="59e2b-112">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="59e2b-112">Setup</span></span>

<span data-ttu-id="59e2b-113">Aby skonfigurować integrację z Power BI, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="59e2b-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="59e2b-114">Zaloguj się do [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="59e2b-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="59e2b-115">Przejdź do **biblioteki udostępnionych aktywów**, wybierz **model raportu Power BI** jako typ składnika aktywów i pobierz pakiet **Globalne księgowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="59e2b-116">Zaloguj się do [PowerBI.com](https://app.powerbi.com/) i wgraj plik raportu **Globalnego księgowania zapasów** Power BI, aby wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="59e2b-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="59e2b-117">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-117">Select **New**.</span></span>
    1. <span data-ttu-id="59e2b-118">Wybierz **Prześlij plik**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="59e2b-119">Wybierz plik raportu **Globalnego księgowanie zapasów** Power BI.</span><span class="sxs-lookup"><span data-stu-id="59e2b-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="59e2b-120">Aby skonfigurować raport **Globalnego księgowanie zapasów** Power BI, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="59e2b-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="59e2b-121">Przejdź do obszaru roboczego **Mój obszar roboczy**, znajdź zestaw danych dla Globalnego księgowania zapasów, a następnie w menu **Opcje** wybierz polecenie **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="59e2b-122">W ustawieniach **Globalnego księgowania zapasów** rozwiń pozycję **Parametry** i w razie potrzeby zaktualizuj wszystkie parametry.</span><span class="sxs-lookup"><span data-stu-id="59e2b-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="59e2b-123">Zarejestruj aplikację zgodnie z opisem w temacie [Konfiguracja integracji PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="59e2b-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="59e2b-124">Aby zintegrować raport **Globalnego księgowanie zapasów** Power BI w Dynamics 365 Supply Chain Management, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="59e2b-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="59e2b-125">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="59e2b-126">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="59e2b-127">Wybierz opcję **Włącz integrację PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="59e2b-128">W polu **Identyfikator aplikacji** wprowadź identyfikator.</span><span class="sxs-lookup"><span data-stu-id="59e2b-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="59e2b-129">W polu **Klucz aplikacji** wprowadź klucz.</span><span class="sxs-lookup"><span data-stu-id="59e2b-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="59e2b-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-130">Select **Save**.</span></span>

1. <span data-ttu-id="59e2b-131">Odśwież stronę, tak aby było wyświetlane okno dialogowe logowania Power BI.</span><span class="sxs-lookup"><span data-stu-id="59e2b-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="59e2b-132">Na karcie **Opcje** wybierz pozycję **Otwórz katalog raportu**, a następnie wybierz plik raportu **Globalne księgowanie zapasów** Power BI, który został przekazany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="59e2b-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="59e2b-133">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="59e2b-133">Refresh the page.</span></span> <span data-ttu-id="59e2b-134">Raport powinien zostać dodany.</span><span class="sxs-lookup"><span data-stu-id="59e2b-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="59e2b-135">Wybierz plik raportu **Globalnego księgowanie zapasów** w **Raporty Power BI**.</span><span class="sxs-lookup"><span data-stu-id="59e2b-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="59e2b-136">Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="59e2b-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
