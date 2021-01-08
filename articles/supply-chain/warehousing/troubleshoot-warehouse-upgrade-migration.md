---
title: Rozwiązywanie problemów z uaktualnieniem i migracją do zaawansowanego zarządzania magazynem
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas uaktualnienia i migracji do zaawansowanego zarządzania magazynem.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d50c6d75ec7cc98109cf81c38ff42b4d2b105b0c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645824"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="ea43f-103">Rozwiązywanie problemów z uaktualnieniem i migracją do zaawansowanego zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="ea43f-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea43f-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas uaktualnienia i migracji do zaawansowanego zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="ea43f-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="ea43f-105">Zgłaszany jest następujący komunikat o błędzie: „java.security.cert.certPathValidatorException: nie znaleziono kotwicy zaufania dla ścieżki certyfikacji”.</span><span class="sxs-lookup"><span data-stu-id="ea43f-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ea43f-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ea43f-106">Issue description</span></span>

<span data-ttu-id="ea43f-107">Ten komunikat o błędzie jest wyświetlany w aplikacji magazynu, ponieważ certyfikaty z podpisem własnym nie są zaufane w systemie Android 8 lub wyższym w środowiskach lokalnych.</span><span class="sxs-lookup"><span data-stu-id="ea43f-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ea43f-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ea43f-108">Issue resolution</span></span>

<span data-ttu-id="ea43f-109">Należy skorzystać z zewnętrznego (publicznego) urzędu certyfikującego (CA).</span><span class="sxs-lookup"><span data-stu-id="ea43f-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="ea43f-110">Poprawka dotycząca tego problemu jest dostępna w wersji 1.9.0.0 aplikacji magazynu.</span><span class="sxs-lookup"><span data-stu-id="ea43f-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="ea43f-111">Aby uzyskać więcej informacji o tym problemie i sposobach jego rozwiązywania, zapoznaj się z tematami [Rozwiązywanie problemów z połączeniem aplikacji magazynowej](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="ea43f-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="ea43f-112">Jaki jest zatwierdzony proces przenoszenia się z magazynu podstawowego do magazynu zaawansowanego?</span><span class="sxs-lookup"><span data-stu-id="ea43f-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="ea43f-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="ea43f-113">Issue description</span></span>

<span data-ttu-id="ea43f-114">Obecnie jest używany moduł zarządzania zapasami/magazynem oraz korzystania z podstawowych funkcji magazynu, a użytkownik chce przejść do zaawansowanej wersji magazynowej w celu wykorzystania urządzeń przenośnych, grup czynności i pracy.</span><span class="sxs-lookup"><span data-stu-id="ea43f-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="ea43f-115">Występują jednak problemy podczas próby dokonania tego przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="ea43f-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="ea43f-116">Na przykład nie można zmienić produktów w taki sposób, aby korzystały z wymiarów magazynowania (oddział, magazyn i lokalizacja), ponieważ produkty mają względem nich transakcje.</span><span class="sxs-lookup"><span data-stu-id="ea43f-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="ea43f-117">W związku z tym należy poznać zatwierdzony proces przenoszenia się z magazynu podstawowego do magazynu zaawansowanego.</span><span class="sxs-lookup"><span data-stu-id="ea43f-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ea43f-118">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ea43f-118">Issue resolution</span></span>

<span data-ttu-id="ea43f-119">Aby uzyskać więcej informacji dotyczących procesu przenoszenia z magazynu podstawowego do magazynu zaawansowanego, należy zapoznać się z poniższymi wpisami blogu i dokumentacją:</span><span class="sxs-lookup"><span data-stu-id="ea43f-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="ea43f-120">Włącz proces zarządzania magazynowego dla istniejących pozycji i magazynów</span><span class="sxs-lookup"><span data-stu-id="ea43f-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="ea43f-121">Migracja Microsoft Dynamics AX WMS do nowej funkcji magazynu i transportu R3</span><span class="sxs-lookup"><span data-stu-id="ea43f-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="ea43f-122">Migracja pozycji WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="ea43f-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="ea43f-123">Uaktualnienie zarządzania magazynem z Microsoft Dynamics AX 2012 do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ea43f-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)
