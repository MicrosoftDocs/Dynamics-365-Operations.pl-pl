---
title: Konfigurowanie pracownika
description: Ta procedura ilustruje sposób konfigurowania pracownika jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży.
author: jblucher
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a21d5f2d5963db2a92b653e8e520f96f11ba1bf6acbb238812211154d5b39fc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726390"
---
# <a name="configure-a-worker"></a>Konfigurowanie pracownika

[!include [banner](../includes/banner.md)]

Ta procedura ilustruje sposób konfigurowania pracownika jako przedstawiciela handlowego, który jest uprawniony do prowizji od sprzedaży w punkcie sprzedaży. Procedura wykorzystuje dane firmy demonstracyjnej USRT.


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
4. Kliknij kartę Commerce.
    * Pracownika można przypisać do domyślnej grupy sprzedaży. Domyślna grupa sprzedaży zostanie automatycznie dodana do wierszy sprzedaży w punkcie sprzedaży, jeśli ta opcja jest włączona w profilu funkcji sklepu.  
5. Kliknij przycisk Edytuj.
6. W polu Grupa domyślna wprowadź lub wybierz wartość.
7. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]