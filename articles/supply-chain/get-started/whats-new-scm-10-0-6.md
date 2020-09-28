---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6 (listopad 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9ee25036488d2f7f24c1691d36239f3f34caf0cb
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802926"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.6 (listopad 2019 r.)

[!include [banner](../includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.6. Ta wersja ma numer kompilacji 10.0.234. W czasie, gdy ogólna Data dostępności jest w listopadzie, nowe funkcje są dostępne do wczesnego wydania w październiku. Aby uzyskać więcej informacji o 10.0.6, zobacz [Dodatkowe zasoby](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Jednostka danych (wersja 2) modeli konfiguracji produktu

Zostanie wydana druga wersja jednostki danych „modele konfiguracji produktu” (zwanej „modelami konfiguracji produktów wer. 2”). Szablon domyślny „418 — modele konfiguracji produktu” również musi być tak, aby korzystał z nowej jednostki danych „modele konfiguracji produktu wer. 2” w szablonach struktury importu/eksportu. Szablon nie zostanie zaktualizowany automatycznie, dzięki czemu będzie konieczne ręczne załadowanie szablonu z poziomu domyślnego. Jednostka wer. 2 eksportuje jeden wiersz jako oddzielny plik w załączniku zamiast w wierszu, rozwiązując ograniczenia rozmiaru jednostki wer.1. 
 
Co należy zrobić, aby wykonać tę zmianę?
-    Ponieważ jednostka wer. 1 jest przestarzała, należy zacząć przeprowadzać migrację z wer. 1 na wer. 2. W przypadku korzystania z szablonu „418 — modele konfiguracji produktów” można kliknąć przycisk „Załaduj szablony domyślne” i ponownie załadować szablon „418 — modele konfiguracji produktów”
-    Jeśli chcesz zachować zgodność z istniejącymi systemami, możesz teraz nadal używać istniejącego szablonu i jednostki (przestarzałe) wer. 1 do czasu przeniesienia integracji do nowego szablonu. 

## <a name="feature-management-enhancements"></a>Poprawki zarządzania funkcjami
Zarządzanie funkcjami pozwala teraz domyślnie włączyć wszystkie nowe funkcje, wymagać potwierdzenia włączenia funkcji i włączyć wszystkie funkcje, które nie zostały jeszcze włączone. 


## <a name="purchase-agreement-responsible-party"></a>Strona odpowiedzialna za umowę zakupu
Obecnie istnieje możliwość zdefiniowania podstawowych i drugorzędnych jednostek odpowiedzialnych w formularzu klasyfikacji umowy zakupu oraz w wynikowych umowach zakupu.  Dzięki temu użytkownicy mogą uzyskać dostęp do osób, którym przewidzisz umowy.

## <a name="rfq-link-on-the-purchase-order-line"></a>Łącze ZO w wierszu zamówienia zakupu
Można dodać łącze odwołania z wierszy zamówienia zakupu z powrotem do odpowiednich wierszy ZO, z których pochodzą, umożliwiając użytkownikowi łatwe udostępnienie zapytanie ofertowe dokumentu pomocniczego.

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="bug-fixes"></a>Poprawki błędów
Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.6, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Aktualizacja platformy Update 30
Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.6 zawiera aktualizację Platform update 30. Aby dowiedzieć się więcej o aktualizacji Platform update 30, zobacz [Nowości lub zmiany w aktualizacji Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: plan wydania 2019 aktualizacja 2
Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zajrzyj do [Dynamics 365: plan wydania 2019 aktualizacja 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.
