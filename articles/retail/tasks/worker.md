---
title: Konfigurowanie pracownika
description: Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 797640b487884fc487582addea274007e4ba7a7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563627"
---
# <a name="configure-a-worker"></a>Konfigurowanie pracownika

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura ilustruje sposób konfigurowania pracownika sieci sprzedaży jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży. Procedura wykorzystuje dane firmy demonstracyjnej USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Tworzenie grupy sprzedaży prowizyjnej dla pracownika
1. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy sprzedaży.
    * Pracowników można przypisać do jednej lub więcej grup sprzedaży. W punkcie sprzedaży można wybierać dowolne grupy sprzedaży zawierające pracowników z książki adresowej sklepu.  
2. Kliknij przycisk Nowy.
3. W polu Grupa wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Kliknij przycisk Zapisz.
6. W okienku akcji kliknij pozycję Ogólne.
7. Kliknij opcję Przedstawiciel handlowy.
    * Grupa sprzedaży może zawierać więcej niż jednego pracownika. Prowizje można dzielić między pracowników na podstawie tego, jak zdefiniowano udział w prowizji.  
8. W polu Nazwa wprowadź lub wybierz wartość.
9. W polu Wielkość prowizji wprowadź liczbę.
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.
12. Zamknij stronę.

## <a name="assign-the-workers-default-sales-group"></a>Przypisywanie pracowników do domyślnej grupy sprzedaży
1. Wybierz kolejno opcje Handel detaliczny i inny > Pracownicy > Wszyscy pracownicy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij kartę Detal.
    * Pracownika można przypisać do domyślnej grupy sprzedaży. Domyślna grupa sprzedaży zostanie automatycznie dodana do wierszy sprzedaży w punkcie sprzedaży, jeśli ta opcja jest włączona w profilu funkcji sklepu.  
5. Kliknij przycisk Edytuj.
6. W polu Grupa domyślna wprowadź lub wybierz wartość.
7. Kliknij przycisk Zapisz.

