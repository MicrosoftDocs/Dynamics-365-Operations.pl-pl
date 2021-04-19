---
title: Konfigurowanie preferowanego technika
description: Można wybrać dowolnego pracownika jako preferowanego technika dla umowy serwisowej lub zlecenia serwisowego.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a517c54214476aed438846c57fe58eb5ec9ef8d1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835733"
---
# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="40b58-103">Konfigurowanie preferowanego technika</span><span class="sxs-lookup"><span data-stu-id="40b58-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="40b58-104">Można wybrać dowolnego pracownika jako preferowanego technika dla umowy serwisowej lub zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="40b58-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="40b58-105">Jednak dobrym rozwiązaniem jest dodawanie pracownika do odpowiedniego zespołu wysyłki, dzięki czemu pracownik jest uwzględniany w formularzu **Pulpit wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="40b58-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="40b58-106">Przypisywanie pracownika do zespołu wysyłki</span><span class="sxs-lookup"><span data-stu-id="40b58-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="40b58-107">Kliknij kolejno opcje **Zasoby ludzkie** \> **Wspólne** \> **Pracownicy** \> **Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="40b58-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="40b58-108">Kliknij dwukrotnie pracownika, aby otworzyć stronę szczegółów pracowników.</span><span class="sxs-lookup"><span data-stu-id="40b58-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="40b58-109">W **okienku akcji** kliknij przycisk kolejno opcje **Ustawienia** \> **Zespół wysyłki**, aby otworzyć formularz **Pracownicy wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="40b58-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="40b58-110">W polu **Zespół wysyłki** wybierz zespół, do którego ma być przypisany pracownik.</span><span class="sxs-lookup"><span data-stu-id="40b58-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="40b58-111">Przypisywanie preferowanego technika do umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="40b58-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="40b58-112">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="40b58-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="40b58-113">Kliknij dwukrotnie umowę serwisową, aby otworzyć formularz szczegółów.</span><span class="sxs-lookup"><span data-stu-id="40b58-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="40b58-114">Na karcie **Ogólne** wybierz pole **Preferowany technik**, a następnie wybierz członka odpowiedniego zespołu wysyłki jako preferowanego serwisanta dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="40b58-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="40b58-115">Przypisywanie preferowanego technika do zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="40b58-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="40b58-116">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Pulpit wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="40b58-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="40b58-117">W formularzu <STRONG>Pulpit wysyłki</STRONG> określ zakres dat działań dyspozytorskich, które chcesz wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="40b58-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="40b58-118">Określ również, czy mają być wyświetlane działania zamknięte, oraz czy lista działań wysyłki ma być ograniczona do zespołów, do których należysz lub które możesz monitorować.</span><span class="sxs-lookup"><span data-stu-id="40b58-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="40b58-119">Kliknij przycisk <STRONG>OK</STRONG>, aby otworzyć formularz <STRONG>Pulpit wysyłki</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="40b58-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="40b58-120">Wybierz wiersz wykonania usługi, który chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="40b58-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="40b58-121">Na karcie **Powiązane** za pomocą listy **Pracownik** przypisz członka odpowiedniego zespołu wysyłki jako preferowanego serwisanta dla zgłoszenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="40b58-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="40b58-122">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="40b58-122">See also</span></span>

[<span data-ttu-id="40b58-123">Omówienie opracowania i ustanawiania przeglądów umów serwisowych</span><span class="sxs-lookup"><span data-stu-id="40b58-123">Develop and establish service agreements overview</span></span>](service-agreements.md)

[<span data-ttu-id="40b58-124">Ręczne tworzenie zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="40b58-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="40b58-125">[Umowy serwisowe (formularz)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="40b58-125">[Service agreements (form)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span></span>
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]