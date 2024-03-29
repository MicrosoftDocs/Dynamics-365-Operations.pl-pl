---
title: Konfigurowanie preferowanego technika
description: Można wybrać dowolnego pracownika jako preferowanego technika dla umowy serwisowej lub zlecenia serwisowego.
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c9495bbc8e5f7cb603c027a125887feba1f0e2d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017211"
---
# <a name="set-up-a-preferred-technician"></a>Konfigurowanie preferowanego technika 

[!include [banner](../includes/banner.md)]


Można wybrać dowolnego pracownika jako preferowanego technika dla umowy serwisowej lub zlecenia serwisowego. Jednak dobrym rozwiązaniem jest dodawanie pracownika do odpowiedniego zespołu wysyłki, dzięki czemu pracownik jest uwzględniany w formularzu **Pulpit wysyłki**.

## <a name="assign-employee-to-a-dispatch-team"></a>Przypisywanie pracownika do zespołu wysyłki

1.  Kliknij kolejno opcje **Zasoby ludzkie** \> **Pracownicy** \> **Pracownicy**. Kliknij dwukrotnie pracownika, aby otworzyć stronę szczegółów pracowników. W **okienku akcji** kliknij przycisk kolejno opcje **Ustawienia** \> **Zespół wysyłki**, aby otworzyć formularz **Pracownicy wysyłki**.

2.  W polu **Zespół wysyłki** wybierz zespół, do którego ma być przypisany pracownik.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Przypisywanie preferowanego technika do umowy serwisowej

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Umowy serwisowe** \> **Umowy serwisowe**. Kliknij dwukrotnie umowę serwisową, aby otworzyć formularz szczegółów.

2.  Na karcie **Ogólne** wybierz pole **Preferowany technik**, a następnie wybierz członka odpowiedniego zespołu wysyłki jako preferowanego serwisanta dla umowy serwisowej.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Przypisywanie preferowanego technika do zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Pulpit wysyłki**.
    

    > [!NOTE]
    > <P>W formularzu <STRONG>Pulpit wysyłki</STRONG> określ zakres dat działań dyspozytorskich, które chcesz wyświetlić. Określ również, czy mają być wyświetlane działania zamknięte, oraz czy lista działań wysyłki ma być ograniczona do zespołów, do których należysz lub które możesz monitorować. Kliknij przycisk <STRONG>OK</STRONG>, aby otworzyć formularz <STRONG>Pulpit wysyłki</STRONG>.</P>



2.  Wybierz wiersz wykonania usługi, który chcesz zmodyfikować.

3.  Na karcie **Powiązane** za pomocą listy **Pracownik** przypisz członka odpowiedniego zespołu wysyłki jako preferowanego serwisanta dla zgłoszenia serwisowego.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie opracowania i ustanawiania przeglądów umów serwisowych](service-agreements.md)

[Ręczne tworzenie zleceń serwisowych](create-service-orders-manually.md)

[Umowy serwisowe (formularz)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]