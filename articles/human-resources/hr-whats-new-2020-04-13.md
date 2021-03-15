---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (13 kwietnia 2020)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 13 kwietnia 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3afc112f8a30bb187fbe37c9062afe7943e986ec
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127904"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (13 kwietnia 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3136. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="new-production-release-cadence"></a>Nowa frekwencja wydania produkcyjnego

Wraz z wejściem wersji z tego tygodnia frekwencja wydwania nowych aktualizacji dla Human Resources przesunie się z cotygodniowej aktualizacji na aktualizację typu dwutygodniowego. Aby zapewnić zgodność z zasadami bezpiecznego wdrażania systemu oraz utrzymywać wysokie standardy stabilności i niezawodności w usłudze, proces wdrażania aktualizacji usług we wszystkich regionach będzie teraz zmieniony na aktualizacje co dwa tygodnie. Na każdym etapie procesu są umieszczone dodatkowe testy i urządzenia kontrolne. Aby uzyskać więcej informacji o frekwencjji aktualizacji wersji, odwiedź [Proces aktualizacji](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>Pole dokładności zaokrąglania nie jest edytowalne po określeniu typu zaokrąglania (435616)

W przypadku zmiany pole **Dokładność zaokrąglania** jest teraz dostępne po zaktualizowaniu pola **Typ zaokrąglania**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Nie można edytować daty zakończenia rejestracji urlopów, gdy plan urlopów nie ma okresów naliczania (413628)

Teraz można edytować datę zakończenia rejestracji bez uzyskiwania błędu „Podstawa daty naliczania pola musi być wypełniona”.

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>Jednostka zatrudnienia nie jest synchronizowana z Dataverse (430834)

Ta zmiana polega na usunięciu usterki, do której nie wykonano synchronizacji z Dataverse danych dotyczących zatrudnienia po dodaniu wymiarów finansowych. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Usuń wiele obiektów nadrzędnych dla jednostki Zakres czasu w kalendarzu roboczym (431775)

Ta zmiana usuwa wiele obiektów nadrzędnych dla jednostki **Zakres czasu w kalendarzu roboczym**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>Filtr z funkcją CAST nie działa w odniesieniu do jednostki Przypisanie pracownika do stanowiska wywołania OData (431699)

Ta aktualizacja zawiera zmianę zezwalającą na Filtrowanie za pomocą funkcji CAST w OData dla jednostki **Przypisanie pracownika do stanowiska**.

## <a name="in-preview"></a>W wersji zapoznawczej

## <a name="leave-suspension"></a>Zawieszenie urlopu

Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego. Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów. Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika. Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Zasady przenoszenia na następny okres

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Znane problemy

## <a name="employment-details-entity"></a>Jednostka szczegółów zatrudnienia

Jednostka **Szczegółów zatrudnienia** została zaktualizowana o następujące pola:

- **Częstotliwość wypłat**
- **Numer identyfikacyjny kategorii zatrudnienia**
- **Typ zatrudnienia**
- **Numer identyfikacyjny typu zatrudnienia**
- **Stan świadczeń zatrudnienia**

Dane konfiguracyjne tych pól zależą od sposobu włączenia funkcji zarządzania świadczeniami w obszarze roboczym **Zarządzanie funkcjami**. Te pola nie powinny być wypełniane ani aktualizowane w jednostce **Szczegółów zatrudnienia**, ponieważ powoduje to błędy podczas importowania.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>Podgląd SharePoint nie działa w niektórych środowiskach

Jeśli Podgląd dokumentów przechowywanych w SharePoint nie działa, spróbuj wykonać poniższą procedurę:

1. Sprawdź, czy konto użytkownika administratora zawiera wiadomość e-mail skojarzoną z rekordem użytkownika. Można przejrzeć te informacje na stronie **Użytkownik**. Jeśli poczta e-mail nie jest skonfigurowana, należy dodać wiadomość e-mail i dostawcę za pomocą dodatku OData dla programu Excel. Domyślnie adres e-mail nie jest obecny w projekcie programu Excel. Musisz edytować projekt programu Excel, dodać wszystkie pola, zastosować je i odświeżyć. Po wykonaniu tych kroków można zaktualizować konto administratora.

2. Gdy konto Administratora ma skojarzone konto e-mail, zaloguj się do modułu Human Resources z poświadczeniami administratora.

3. Aby uruchomić podgląd dokumentu, uzyskaj dostęp do załącznika SharePoint.

4. Zaloguj się przy użyciu konta innego użytkownika, które ma dostęp do załączników i sprawdź, czy podgląd działa zgodnie z oczekiwaniami.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]