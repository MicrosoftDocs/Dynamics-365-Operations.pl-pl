---
title: Sprawdź, czy w aplikacjach Finance and Operations i Common Data Service jest skonfigurowany tryb podwójnego zapisu
description: W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172652"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="9876d-103">Sprawdź, czy w aplikacjach Finance and Operations i Common Data Service jest skonfigurowany tryb podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="9876d-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="9876d-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9876d-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="9876d-105">W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9876d-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="9876d-106">Sprawdź, czy w aplikacji Finance and Operations jest skonfigurowany tryb podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="9876d-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="9876d-107">Aby określić, czy błędy widoczne podczas próby zapisania rekordów do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="9876d-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="9876d-108">Jeśli masz uprawnienia administratora w aplikacji Finance and Operations, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**.</span><span class="sxs-lookup"><span data-stu-id="9876d-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="9876d-109">Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map jednostek, skonfigurowano podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="9876d-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik ma uprawnienia administratora](media/verify_fin_ops_1.png)

+ <span data-ttu-id="9876d-111">Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki \<nazwa jednostki\>*.</span><span class="sxs-lookup"><span data-stu-id="9876d-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="9876d-112">W przykładzie na poniższej ilustracji nie można utworzyć rekordu odbiorcy w aplikacji Finance and Operations, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9876d-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik nie ma uprawnienia administratora](media/verify_fin_ops_2.png)

<span data-ttu-id="9876d-114">Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach Finance and Operations, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="9876d-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="9876d-115">Sprawdź, czy w Common Data Service jest skonfigurowany tryb podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="9876d-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="9876d-116">Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia pola **Firma** na stronach w Common Data Service zostanie skonfigurowany podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="9876d-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![Trwa weryfikowanie połączenia Common Data Service](media/verify_cds.png)

<span data-ttu-id="9876d-118">Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Common Data Service, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="9876d-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="9876d-119">Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Common Data Service, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Common Data Service w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="9876d-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
