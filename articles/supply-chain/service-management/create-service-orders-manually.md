---
title: Ręczne tworzenie zleceń serwisowych
description: Zlecenia serwisowe można tworzyć ręcznie na podstawie umowy serwisowej lub za pomocą formularza **Zlecenia serwisowe**.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 486b4a0291ca527e647c9b5a41ff2e65a7820291
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817588"
---
# <a name="create-service-orders-manually"></a>Ręczne tworzenie zleceń serwisowych    

[!include [banner](../includes/banner.md)]


Zlecenia serwisowe można tworzyć ręcznie na podstawie umowy serwisowej lub za pomocą formularza **Zlecenia serwisowe**. Można również utworzyć zlecenie serwisowe na podstawie projektu.

> [!TIP]
> <P>Do tworzenia zleceń serwisowych można używać zautomatyzowanych procesów. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Tworzenie zlecenia serwisowego ręcznie na podstawie umowy serwisowej

1.  Wybierz **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Wybierz umowę serwisową lub utwórz nową umowę.

3.  Wybierz **Dostarcz**, a następnie w grupie **Tworzenie** wybierz opcję **Planowane zlecenia serwisowe**, a zostanie otwarty formularz **Utwórz zlecenia serwisowe**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Tworzenie zlecenia serwisowego ręcznie w formularzu Zlecenia serwisowe

1.  Wybierz **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz pozycję **Nowy**, aby utworzyć nowe zamówienie usługi.

3.  Utwórz wiersze zlecenia serwisowego dla zlecenia.

> [!NOTE]
> <P>Jeśli pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> jest zaznaczone, można księgować transakcje z wierszy zlecenia serwisowego, nie dołączając do zlecenia serwisowego umowy serwisowej. Jeżeli nie zaznaczono tego pola wyboru, przed zaksięgowaniem wierszy zlecenia serwisowego należy dołączyć do projektu zlecenie serwisowe utworzone ręcznie.</P>

## <a name="create-a-service-order-from-a-project"></a>Tworzenie zlecenia serwisowego na podstawie projektu

1.  Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.

2.  W formularzu **Projekty** w **okienku akcji** wybierz kartę **Zarządzaj** \> wybierz kolejno opcje **Serwis** \> **Zlecenia serwisowe**.

3.  Postępuj zgodnie z poprzednią procedurą ręcznego tworzenia zlecenia serwisowego na podstawie formularza **Zlecenia serwisowe**. W polu **Identyfikator projektu** jest wyświetlane odwołanie do projektu.

> [!NOTE]
> <P>Jeśli pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> jest zaznaczone, można księgować transakcje z wierszy zlecenia serwisowego, nie dołączając do zlecenia serwisowego umowy serwisowej. Jeżeli nie zaznaczono tego pola wyboru, przed zaksięgowaniem wierszy zlecenia serwisowego należy dołączyć do projektu zlecenie serwisowe utworzone ręcznie.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Tworzenie zlecenia serwisowego na podstawie formularza Zamówienie sprzedaży

Zlecenie serwisowe można utworzyć na podstawie formularza **Zamówienia sprzedaży**, używając kreatora **Utwórz nowe zlecenie serwisowe na podstawie zamówienia sprzedaży**.

1.  Przejdź do **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.

2.  Otwórz odnośne zamówienie sprzedaży.

3.  Na karcie **Zamówienie sprzedaży** wybierz **Zlecenie serwisowe**, aby uruchomić kreatora **Utwórz nowe zlecenie serwisowe na podstawie zamówienia sprzedaży**.

4.  Wybierz **Dalej \>**, a następnie wykonaj następujące kroki na stronie **Wybierz umowę dla zlecenia serwisowego**:
    
      - Użyj pola **Umowa serwisowa** w celu wybrania umowy serwisowej, z którą będzie skojarzone nowe zlecenie serwisowe.
    
      - Opcjonalnie: Użyj pola **Identyfikator projektu** w celu skojarzenia tego zlecenia serwisowego z określonym projektem.

5.  Wybierz **Dalej \>**, a następnie wykonaj następujące kroki na stronie **Utwórz zlecenie serwisowe**:
    
      - W polu **Preferowany czas serwisu** wprowadź datę i godzinę rozpoczęcia serwisu.
    
      - Opcjonalnie: Zmodyfikuj tekst w polu **Opis**. Domyślnie to pole zawiera opis umowy serwisowej wybranej na poprzedniej stronie.
    
      - W polu **Osoba odpowiedzialna** wybierz identyfikator pracownika odpowiedzialnego za umowę oraz — jeśli znasz — wprowadź identyfikator preferowanego przez klienta serwisanta mającego się zająć zgłoszeniem serwisowym.
    
      - W polu **Identyfikator kontaktu** wybierz osobę w firmie klienta, z którą należy kontaktować się w sprawach dotyczących danego zlecenia serwisowego.

6.  Wybierz przycisk **Dalej\>**, a następnie **Zakończ**.


## <a name="see-also"></a>Informacje dodatkowe

[Zlecenia serwisowe](service-orders.md)

[Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md)

[Utwórz zlecenia serwisowe (formularz klasy)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]