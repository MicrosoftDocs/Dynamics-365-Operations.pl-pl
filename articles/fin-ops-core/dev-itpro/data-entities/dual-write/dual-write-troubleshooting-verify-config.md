---
title: Weryfikowanie konfiguracji podwójnego zapisu w aplikacjach Finance and Operations i Dataverse
description: W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 361d6555b60e02832c337b6f416b2b3627b6d365
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129314"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="02293-103">Weryfikowanie konfiguracji podwójnego zapisu w aplikacjach Finance and Operations i Dataverse</span><span class="sxs-lookup"><span data-stu-id="02293-103">Verify dual-write configuration in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="02293-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="02293-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="02293-105">W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="02293-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="02293-106">Sprawdź, czy w aplikacji Finance and Operations jest skonfigurowany tryb podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="02293-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="02293-107">Aby określić, czy błędy widoczne podczas próby zapisania wierszy do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="02293-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="02293-108">Jeśli masz uprawnienia administratora w aplikacji Finance and Operations, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**.</span><span class="sxs-lookup"><span data-stu-id="02293-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="02293-109">Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map tabeli, skonfigurowano podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="02293-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik ma uprawnienia administratora](media/verify_fin_ops_1.png)

+ <span data-ttu-id="02293-111">Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki nazwa jednostki.\<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="02293-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="02293-112">W przykładzie na poniższej ilustracji nie można utworzyć wiersza odbiorcy w aplikacji Finance and Operations, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="02293-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik nie ma uprawnienia administratora](media/verify_fin_ops_2.png)

<span data-ttu-id="02293-114">Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach Finance and Operations, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="02293-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="02293-115">Sprawdź, czy w Dataverse jest skonfigurowany tryb podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="02293-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="02293-116">Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia kolumny **Firma** na stronach w Dataverse zostanie skonfigurowany podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="02293-116">When you create data, if you see the **Company** column on pages in Dataverse, dual-write is configured.</span></span>

![Trwa weryfikowanie połączenia Dataverse](media/verify_cds.png)

<span data-ttu-id="02293-118">Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Dataverse, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="02293-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="02293-119">Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Dataverse, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Dataverse w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="02293-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>
