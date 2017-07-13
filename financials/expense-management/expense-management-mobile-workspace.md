---
title: "Mobilny obszar roboczy Zarządzanie wydatkami"
description: "W tym temacie omówiono mobilny obszar roboczy Zarządzanie wydatkami, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Finance and Operations. Ten obszar roboczy pozwala użytkownikom rejestrować i przekazywać paragony, dzięki czemu można je później dołączać do raportów z wydatków. Ponadto w tym mobilnym obszarze roboczym użytkownicy mogą szybko tworzyć wiersze wydatków za pomocą dołączonych paragonów."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0e52d1c5dde7f79c4a8ac5ac2d9c3b25bba9c2cd
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Mobilny obszar roboczy Zarządzanie wydatkami
<a id="expense-management-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie omówiono mobilny obszar roboczy Zarządzanie wydatkami, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Finance and Operations. Ten obszar roboczy pozwala użytkownikom rejestrować i przekazywać paragony, dzięki czemu można je później dołączać do raportów z wydatków. Ponadto w tym mobilnym obszarze roboczym użytkownicy mogą szybko tworzyć wiersze wydatków za pomocą dołączonych paragonów.

Omówienie komórkowego obszaru roboczego Zarządzanie wydatkami
<a id="overview-of-the-expense-management-mobile-workspace" class="xliff"></a>
---------------------------------------------------

Wiele organizacji wymaga, aby kopie paragonów były dołączane do raportów o wydatkach z podróży lub wydatkach biznesowych, które pracownicy składają w celu uzyskania zwrotu pieniędzy. Mobilny obszar roboczy **Zarządzanie wydatkami** pozwala użytkownikom szybko tworzyć nowe wiersze wydatków na dowolnych urządzeniach komórkowych za pomocą dołączonej fotografii paragonu. Alternatywnie użytkownicy mogą zarejestrować zdjęcie paragonu i później dołączyć je do raportu z wydatków. W szczególności mobilny obszar roboczy **Zarządzanie wydatkami** oferuje następujące możliwości:

-   Wykonanie zdjęcia paragonu i przekazanie go do programu Microsoft Dynamics 365 for Finance and Operations. Użytkownik może później załączyć to zdjęcie do raportu z wydatków.
-   Przekazanie pliku jako zarejestrowanego paragonu. Użytkownik może później załączyć ten plik do raportu z wydatków.
-   Utworzenie nowego wiersza wydatku za pomocą dołączonego paragonu. Użytkownik można później dodać pozycję wiersza do raportu z wydatków i przesłać raport do zatwierdzenia w celu otrzymania zwrotu pieniędzy.

Pozostałe sekcje w tym temacie opisują wdrażanie i używanie mobilnego obszaru roboczego **Zarządzanie wydatkami**.

## Wymagania wstępne
<a id="prerequisites" class="xliff"></a>
Aby można było wdrożyć mobilny obszar roboczy **Zarządzanie wydatkami**, administrator systemu musi zapewnić spełnienie następujących warunków wstępnych:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Należy zainstalować program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą.</td>
<td>Administrator systemu</td>
<td>Jeśli w organizacji jeszcze nie wdrożono programu Finance and Operations, administrator systemu powinien przeczytać temat <a href="/dynamics365/unified-operations/dev-itpro/deployment/deploy-demo-environment">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Finance and Operations</a>.</td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4019015.</td>
<td>Administrator systemu</td>
<td>KB 4019015 (aktualizacja platformy języka X++ lub poprawka metadanych) zawiera cztery komórkowe obszary robocze dla zarządzania łańcuchem dostaw. W celu zainstalowania poprawki KB 4019015 administrator systemu musi wykonać następującą procedurę:
<ol>
<li>Pobierz poprawkę KB 4019015 z usługi Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający modele <strong>ApplicationSuite</strong> i <strong>ExpenseMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a> do systemu Finance and Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Zarządzanie wydatkami</strong> musi zostać opublikowany w aplikacji komórkowej Finance and Operations.</td>
<td>Administrator systemu</td>
<td><ol>
<li>Uruchom program Finance and Operations w przeglądarce.</li>
<li>Na stronie <strong>Parametry systemu</strong> zaznacz opcję <strong>Zarządzaj mobilnymi obszarami roboczymi</strong>.</li>
<li>Wybierz obszar roboczy <strong>Zarządzanie wydatkami</strong>.</li>
<li>Kliknij opcję <strong>Opublikuj mobilny obszar roboczy</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## Pobieranie i instalowanie aplikacji komórkowej Finance and Operations
<a id="download-and-install-the-finance-and-operations-mobile-app" class="xliff"></a>
W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Finance and Operations.

-   Telefony z systemem Android: [Finance and Operations w sklepie Google Play](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Telefony iPhone: [Finance and Operations w sklepie z aplikacjami iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## Logowanie w aplikacji komórkowej Finance and Operations
<a id="sign-in-to-the-finance-and-operations-mobile-app" class="xliff"></a>
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Finance and Operations.
3.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
4.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Finance and Operations. Wprowadź swoje poświadczenia.
5.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, można wykonać operację ściągania i odświeżyć listę komórkowych obszarów roboczych. 

[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Rejestrowanie paragonu za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami
<a id="capture-a-receipt-by-using-the-expense-management-mobile-workspace" class="xliff"></a>
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zarządzanie wydatkami**.
2.  Wybierz opcję **Zarejestruj paragon**.
3.  Wybierz opcję **Zrób zdjęcie** lub **Wybierz obraz**.
4.  Jeśli wybrano opcję **Zrób zdjęcie**, wykonaj następujące kroki:
    1.  Uruchamiasz aparat w swoim urządzeniu komórkowym, aby można było sfotografować paragon. Po zakończeniu robienia zdjęcia kliknij przycisk **OK**, aby zaakceptować zdjęcie.
    2.  Opcjonalnie: Nadaj fotografii nazwę i ewentualnie wprowadź notatki.

     **Lub:**  W przypadku wybrania opcji **Wybierz obraz** wykonaj następujące kroki:
    1.  Wybierz zdjęcie z listy.
    2.  Opcjonalnie: Nadaj zdjęciu nazwę i ewentualnie wprowadź notatki.

5.  Wybierz opcję **Gotowe**.

## Szybkie wprowadzanie wydatku za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami
<a id="quick-expense-entry-by-using-the-expense-management-mobile-workspace" class="xliff"></a>
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zarządzanie wydatkami**.
2.  Wybierz opcję **Szybkie wprowadzanie wydatku**.
3.  Wybierz kategorię wydatku. Zobaczysz listę kategorii wydatków załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych maksymalnie 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Jeśli żądanej kategorii nie ma na liście, wybierz opcję **Szukaj**, aby wykonać wyszukiwanie online w usłudze Finance and Operations. Poszukaj według kategorii wydatków lub przejdź do wyszukiwania według typu wydatku.
4.  Wprowadź datę transakcji wydatkowej.
5.  Opcjonalnie: Wprowadź handlowca dla wydatku.
6.  Wprowadź kwotę wydatku.
7.  Wybierz walutę wydatku. Zobaczysz listę kodów walut załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych maksymalnie 400 walut, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Jeśli żądanej waluty nie ma na liście, wybierz opcję **Szukaj**, aby wykonać wyszukiwanie online w usłudze Finance and Operations. Wyszukaj według waluty lub przełącz się do wyszukiwania według nazwy.
8.  Wybierz opcję **Zrób zdjęcie** lub **Wybierz obraz**.
9.  Jeśli wybrano opcję **Zrób zdjęcie**, zostanie uruchomiony aparat w swoim urządzeniu komórkowym, aby można było sfotografować paragon. Po zakończeniu robienia zdjęcia kliknij przycisk **OK**, aby zaakceptować zdjęcie.  lub  W przypadku wybrania opcji **Wybierz obraz** wybierz obraz z listy.
10. Wybierz opcję **Gotowe**.






