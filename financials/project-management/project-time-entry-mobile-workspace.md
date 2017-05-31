---
title: Mobilny obszar roboczy Wprowadzanie czasu projektu dla aplikacji Dynamics 365 for Operations
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Wprowadzanie czasu projektu. Ten obszar roboczy umożliwia użytkownikom wprowadzanie i zapisywanie czasu względem projektu za pomocą ich urządzeń przenośnych."
author: annbe
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9c592c301908898915164e9236850759b73543fe
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Mobilny obszar roboczy Wprowadzanie czasu projektu

[!include[banner](../includes/banner.md)]



W tym temacie omówiono mobilny obszar roboczy Wprowadzanie czasu projektu przeznaczony dla aplikacji komórkowej Dynamics 365 for Operations. Ten obszar roboczy umożliwia użytkownikom wprowadzanie i zapisywanie czasu względem projektu za pomocą ich urządzeń przenośnych.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Omówienie mobilnego obszaru roboczego Wprowadzanie czasu projektu
---------------------------------------------------

W ramach swojej codziennej pracy członkowie zespołu projektu często przebywają na miejscu realizacji lub są w podróży. Mobilny obszar roboczy **Wprowadzanie czasu projektu** pozwala użytkownikom wprowadzać czas pracy w projekcie podlegający i niepodlegający fakturowaniu na dowolnych urządzeniach komórkowych. Dzięki temu członkowie zespołu projektu mogą rejestrować przepracowany czas w dowolnym miejscu i czasie. Mogą również wyświetlać wpisy czasu, które zostały już zarejestrowane. 

W szczególności mobilny obszar roboczy **Wprowadzanie czasu projektu** oferuje następujące funkcje:

-   Dla każdej wybranej daty można wprowadzić liczbę godzin spędzonych nad konkretnymi zadaniami.
-   Wyszukiwanie według nazwy projektu lub odbiorcy w celu znalezienia projektu, dla którego ma zostać wprowadzony czas.
-   Określanie kategorii i działania, na które poświęcono czas.
-   Rejestrowanie czasu jako podlegającego lub niepodlegającego zafakturowaniu dla projektu.
-   Opcjonalne wprowadzanie komentarzy wewnętrznych lub zewnętrznych.

Aby wdrożyć mobilny obszar roboczy **Wprowadzanie czasu projektu**, zobacz następujące sekcje w tym temacie:

## <a name="prerequisites"></a>Wymagania wstępne
Aby można było wdrożyć mobilny obszar roboczy **Wprowadzanie czasu projektu**, administrator systemu musi zapewnić spełnienie następujących warunków wstępnych:

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
<td>Jeśli w organizacji jeszcze nie wdrożono programu Dynamics 365 for Operations, administrator systemu powinien przeczytać temat <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4018050.</td>
<td>Administrator systemu</td>
<td>KB 4018050 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Wprowadzanie czasu projektu</strong>. W celu zainstalowania poprawki KB 4018050 administrator systemu musi wykonać następującą procedurę:
<ol>
<li>Pobierz poprawkę KB 4018050 z usługi Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający modele <strong>ApplicationSuite</strong> i <strong>ProjectMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a> do systemu Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Wprowadzanie czasu projektu</strong> musi zostać opublikowany w aplikacji komórkowej Dynamics 365 for Operations.</td>
<td>Administrator systemu</td>
<td><ol>
<li>Uruchom program Dynamics 365 for Operations w przeglądarce internetowej.</li>
<li>Na stronie <strong>Parametry systemu</strong> na karcie <strong>Zarządzaj mobilnymi obszarami roboczymi</strong> zaznacz obszar roboczy <strong>Wprowadzanie czasu projektu</strong>.</li>
<li>Kliknij opcję <strong>Opublikuj mobilny obszar roboczy</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Pobieranie i instalowanie aplikacji komórkowej Dynamics 365 for Operations
W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Dynamics 365 for Operations.

-   Android: [Dynamics 365 for Operations w sklepie Google Play](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   iPhone: [Dynamics 365 for Operations w sklepie z aplikacjami iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Logowanie do aplikacji komórkowej Dynamics 365 for Operations
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL programu Dynamics 365 for Operations.
3.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
4.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Dynamics 365 for Operations. Wprowadź swoje poświadczenia.
5.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, można wykonać operację ściągania i odświeżyć listę komórkowych obszarów roboczych.

[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Wprowadzanie czasu za pomocą mobilnego obszaru roboczego Wprowadzanie czasu projektu
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Wprowadzanie czasu projektu**.
2.  Wybierz opcję **Wpis czasu**. Zobaczysz daty kalendarzowe bieżącego tygodnia.
3.  Dla wybranej daty wybierz kolejno opcje **Akcje** &gt; **Nowy wpis**.
4.  Wpisz liczbę godzin, która ma zostać zarejestrowana.
5.  Wybierz projekt, dla którego wprowadzasz czas. Zobaczysz listę projektów załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Jeśli żądanego projektu nie ma na liście, wybierz opcję **Szukaj**, aby wykonać wyszukiwanie online w usłudze Dynamics 365 for Operations. Poszukaj według nazwy lub przejdź do wyszukiwania według nazwy projektu lub odbiorcy.
7.  Umożliwia wybór kategorii. Zobaczysz listę kategorii załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Jeśli żądanej kategorii nie ma na liście, wybierz opcję **Szukaj**, aby wykonać wyszukiwanie online w usłudze Dynamics 365 for Operations. Wyszukaj według kategorii lub przełącz się do wyszukiwania według nazwy kategorii.
9.  Wybierz działanie. Zobaczysz listę działań załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Jeśli żądanego działania nie ma na liście, wybierz opcję **Szukaj**, aby wykonać wyszukiwanie online w usłudze Dynamics 365 for Operations. Wyszukaj według numeru działania lub przełącz się do wyszukiwania według celu.
11. Wybierz właściwość wiersza.
12. Opcjonalne: Wprowadź komentarze wewnętrzne i zewnętrzne.
13. Wybierz opcję **Gotowe**.






