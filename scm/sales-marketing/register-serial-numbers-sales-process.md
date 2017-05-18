---
title: "Rejestrowanie numerów seryjnych w procesie sprzedaży"
description: "Ten artykuł wyjaśnia sposób rejestrowania numerów seryjnych na dokumentach dostawy i fakturach w procesie sprzedaży. Ta funkcja jest przydatna, gdy firma chce zapisywać numery seryjne na potrzeby serwisu i gwarancji, ale nie chce nimi zarządzać w zapasach na etapach od przyjęcia do wydania."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: de1d8bc2fa1080e549cb8c33657ad0f373644d38
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="register-serial-numbers-in-the-sales-process"></a>Rejestrowanie numerów seryjnych w procesie sprzedaży

[!include[banner](../includes/banner.md)]


Ten artykuł wyjaśnia sposób rejestrowania numerów seryjnych na dokumentach dostawy i fakturach w procesie sprzedaży. Ta funkcja jest przydatna, gdy firma chce zapisywać numery seryjne na potrzeby serwisu i gwarancji, ale nie chce nimi zarządzać w zapasach na etapach od przyjęcia do wydania.

Wiele firm po prostu chce gromadzić numery seryjne na potrzeby serwisu i gwarancji, i nie musi przechowywać numerów seryjnych w magazynie od przyjęcia do wydania. W tych scenariuszach program Microsoft Dynamics 365 for Operations umożliwia rejestrowanie numerów seryjnych na dokumentach dostawy i fakturach, gdy produkty są sprzedawane. Jeśli produkty są potem zwracane, można śledzić każdy produkt do faktury w celu ustalenia, czy produkt został sprzedany przez organizację oraz określenia, czy zobowiązania wynikające z usługi lub gwarancji są prawidłowe.
Czy istnieją wymagania wstępne?
----------------------------

Numery seryjne dla procesu sprzedaży trzeba włączyć, wybierając opcję **Aktywny w procesie sprzedaży** na stronie **Grupy wymiarów śledzenia**. W programie Microsoft Dynamics 365 for Operations mogą występować następujące zdarzenia:
-   Na skróconej karcie **Numery seryjne** opcja **Kontrola numeru seryjnego** jest zaznaczona. Jeśli ta opcja jest zaznaczona, należy zarejestrować jeden numer seryjny dla każdego towaru na dokumencie dostawy lub fakturze.
-   Wszystkie wybrane opcje w grupie wymiaru śledzenia dla numerów seryjnych zostały wyczyszczone, z wyjątkiem opcji **Dozwolony pusty rozchód**. Można zaznaczyć opcję **Dozwolony pusty rozchód**, aby zastąpić kontrolę numeru seryjnego i zezwalać na pakowanie i fakturowanie produktów bez rejestrowania numerów seryjnych.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>Kiedy należy rejestrować numery seryjne w procesie sprzedaży?
Numery seryjne można zarejestrować na dokumencie dostawy dla zamówienia sprzedaży lub faktury. Podczas przygotowywania dla towaru seryjnego faktury, która została wysłana z dokumentem dostawy, można wybrać, które z numerów seryjnych na dokumencie dostawy dodać do faktury. Ilość zarejestrowanych numerów seryjnych nie może przekroczyć ilości wysłanych towarów. W przypadku tworzenia faktury częściowej, można wybrać mniej towarów seryjnych niż zostało zarejestrowane w dokumencie dostawy. Podczas drukowania dokumentu dostawy lub faktury, numery seryjne, które zostały zarejestrowane, są uwzględniane.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>Czy można wprowadzać numery seryjne przez skanowanie je lub trzeba je wpisać?
Można skanować numery seryjne lub wpisywać je ręcznie. Tryb skanowania określa, czy numery seryjne mają być dodawane czy usuwane z listy numerów seryjnych na fakturze lub dokumencie dostawy. W celu skanowania numerów seryjnych, na przykład przy użyciu ręcznego skanera kodu kreskowego, należy skonfigurować skaner do wysyłania polecenia Enter lub TAB po numerze seryjnym. To polecenie wskazuje koniec strumienia danych. W przeciwnym razie należy nacisnąć klawisz Enter lub TAB na klawiaturze po zeskanowaniu każdego numeru seryjnego.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Jeśli dla procesu sprzedaży włączone zostaną numery seryjne, czy to znaczy, że muszę rejestrować wszystkie numery seryjne dla wszystkich towarów?
Konfiguracja grupy wymiarów śledzenia, która jest przypisana do tego produktu, określa, czy numery seryjne muszą być rejestrowane dla wszystkich pozycji na dokumencie dostawy lub faktury. Po włączeniu numerów seryjnych w procesie sprzedaży, opcja **Kontrola numeru seryjnego** jest automatycznie zaznaczona. Oznacza to, że użytkownik musi zarejestrować jeden numer seryjny albo zarejestrować pustą wartość dla nieczytelnego numeru dla każdego towaru na dokumencie dostawy lub fakturze. Jeśli nie chcesz wymagać numeru seryjnego dla każdego towaru, zaznacz pole wyboru **Dozwolony pusty rozchód** w grupie wymiaru śledzenia, która jest przypisana do towaru. Następnie można zarejestrować mniejszą ilość numerów seryjnych od ilości dostarczanych zapasów. W przypadku zarejestrowania większej ilości numerów seryjnych od ilości wysyłanych towarów, nie będzie można zaksięgować dokumentu dostawy lub faktury.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>Czy można zarejestrować numery seryjne dla faktur częściowych i dostaw częściowych?
Można utworzyć częściowe faktury i dokumenty dostawy dla zamówień sprzedaży i zarejestrować tylko numery seryjne dla towarów, które są objęte fakturami i dokumentami dostawy. Aby utworzyć fakturę częściową w przypadku posiadania więcej niż jednego dokumentu dostawy dla zamówienia sprzedaży, można umieścić numery seryjne z więcej niż jednego dokumentu dostawy. Jednak może istnieć tylko jeden dokument dostawy, na którym nie są uwzględniane wszystkie numery seryjne. Na przykład, jeśli istnieją trzy dokumenty dostawy i każda zawiera dwa towary seryjne, nie można utworzyć faktury częściowej dla jednego towaru z każdego dokumentu dostawy.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>Co należy zrobić, jeśli numer seryjny nie jest czytelny?
Jeśli numeru seryjnego nie można odczytać ani zeskanować, można utworzyć pusty wiersz dla pozycji, klikając przycisk **Nie można odczytać** na stronie **Numery seryjne**. Jeśli numer seryjny stanie się dostępny później, można zaktualizować fakturę lub dokument dostawy. Aby uzyskać więcej informacji zobacz następną sekcję „Czy można poprawić lub zmienić numery seryjne, które zostały zarejestrowane dla zamówienia sprzedaży?”

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>Czy można poprawić lub zmienić numery seryjne, które zostały zarejestrowane dla zamówienia sprzedaży?
Tak, można poprawić numery seryjne, o ile spełnione są następujące warunki:
-   **Faktury** — można zmienić numery seryjnych dla towarów, które nie zostały jeszcze zafakturowane. Dokument dostawcy jest również aktualizowany. Jednak, jeśli wiersz zamówienia sprzedaży został poprawiony poprzez rejestrację ilości ujemnej, nie można zmienić numerów seryjnych dla wiersza zamówienia sprzedaży.
-   **Dokumenty dostawy** — nie można częściowo zmieniać wiersza dokumentu dostawy, który zawiera towary seryjne. Musisz wycofać pełną ilość dla wiersza. Jeśli dokument dostawy został anulowany lub skorygowany, nie trzeba ponownie zarejestrować wycofanych numerów seryjnych podczas tworzenia nowego dokumentu dostawy dla tych samych zapasów seryjnych. Zostaną użyte liczby, które zostały zarejestrowane.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>Czy można wyświetlać numery seryjne, które zostały wysłane razem z określonym dokumentem dostawy lub zostały uwzględnione na fakturze?
Tak, można uruchomić zapytanie na wierszu arkusza dokumentu dostawy lub wierszy arkusza faktury w celu wyświetlenia listy wszystkich numerów seryjnych, które zostały uwzględnione w dokumencie.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>Czy mogę wyświetlić dostępne towary seryjne?
Nie, nie można wyświetlić towarów seryjnych, które użytkownik ma na stanie, ponieważ numery seryjne nie są rejestrowane dla towarów przed momentem ich sprzedaży.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>Czy mogę rejestrować numery seryjnych dla towarów w ilości efektywnej?
Nie, w procesie sprzedaży nie można zarejestrować numerów seryjnych dla towarów w ilości efektywnej. Oprócz tego, jeśli produkt jest skonfigurowany jako towar w ilości efektywnej, nie można przypisać produktu do śledzenia grupy wymiarów, która jest konfigurowana do używania numerów seryjnych tylko podczas procesu sprzedaży.
Czy mogę zarejestrować numer seryjny w punkcie sprzedaży sieci sprzedaży?
------------------------------------------------

Tak, w punkcie sprzedaży sieci sprzedaży będzie wyświetlany monit o wprowadzenie numeru seryjnego, gdy użytkownik sprzedaje pozycję skojarzoną z grupą śledzenia skonfigurowaną do używania numerów seryjnych tylko podczas procesu sprzedaży.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Jakie role zabezpieczeń są wymagane do rejestrowania numerów seryjnych w trakcie procesu sprzedaży?
Ta funkcjonalność jest dostępna dla wszystkich ról, które mogą obsługiwać dokumenty dostawy sprzedaży i faktury sprzedaży. Poniższe obowiązki umożliwiają pracownikom korygowanie numerów seryjnych i rejestrowanie pustych wpisów dla numerów seryjnych, których nie można odczytać lub zeskanować:
-   Obsługa korekt numerów seryjnych
-   Obsługa rejestracji nieczytelnych numerów seryjnych






