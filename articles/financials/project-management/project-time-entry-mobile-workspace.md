---
title: Mobilny obszar roboczy Wprowadzanie czasu projektu
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Wprowadzanie czasu projektu. Ten obszar roboczy umożliwia użytkownikom wprowadzanie i zapisywanie czasu względem projektu za pomocą ich urządzeń przenośnych."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: c04ffccdcbf104b1d5db30a41116663fcedd4e1d
ms.contentlocale: pl-pl
ms.lasthandoff: 12/01/2017

---

# <a name="project-time-entry-mobile-workspace"></a>Mobilny obszar roboczy Wprowadzanie czasu projektu

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Wprowadzanie czasu projektu**. Ten obszar roboczy umożliwia użytkownikom wprowadzanie i zapisywanie czasu względem projektu za pomocą ich urządzeń przenośnych.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations. 

## <a name="overview"></a>Przegląd
W ramach swojej codziennej pracy członkowie zespołu projektu często przebywają na miejscu realizacji lub są w podróży. Mobilny obszar roboczy **Wprowadzanie czasu projektu** pozwala użytkownikom wprowadzać czas pracy w projekcie podlegający i niepodlegający fakturowaniu na dowolnych urządzeniach komórkowych. Dzięki temu członkowie zespołu projektu mogą rejestrować przepracowany czas w dowolnym miejscu i czasie. Mogą również wyświetlać wpisy czasu, które zostały już zarejestrowane. 

W szczególności w mobilnym obszarze roboczym **Wprowadzanie czasu projektu** użytkownicy mogą wykonywać następujące zadania:

-   Dla każdej wybranej daty można wprowadzić liczbę godzin spędzonych nad konkretnymi zadaniami.
-   Wyszukiwanie według nazwy projektu lub odbiorcy w celu znalezienia projektu, dla którego ma zostać wprowadzony czas.
-   Określanie kategorii i działania, na które poświęcono czas.
-   Rejestrowanie czasu jako podlegającego lub niepodlegającego zafakturowaniu dla projektu.
-   Opcjonalne wprowadzanie komentarzy wewnętrznych lub zewnętrznych.

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Warunki wstępne w przypadku korzystania z programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, administrator systemu musi opublikować mobilny obszar roboczy **Wprowadzanie czasu projektu**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne. 

<table>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td>Zainstalowanie poprawki KB 4018050.</td>
<td>Administrator systemu</td>
<td>KB 4018050 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Wprowadzanie czasu projektu</strong>. W celu zainstalowania poprawki KB 4018050 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający modele <strong>ApplicationSuite</strong> i <strong>ProjectMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Wprowadzanie czasu projektu</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

-   [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Wprowadzanie czasu za pomocą mobilnego obszaru roboczego Wprowadzanie czasu projektu
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Wprowadzanie czasu projektu**.
2.  Wybierz opcję **Wpis czasu**. Zostaną wyświetlone daty kalendarzowe bieżącego tygodnia.
3.  Dla wybranej daty wybierz kolejno opcje **Akcje** &gt; **Nowy wpis**.
4.  Wpisz liczbę godzin, która ma zostać zarejestrowana.
5.  Wybierz projekt, dla którego wprowadzasz czas. Zostanie wyświetlona lista projektów załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, zobacz [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Jeśli Twojego projektu nie ma na liście, kliknij przycisk **Szukaj**. Poszukaj według nazwy lub przejdź do wyszukiwania według nazwy projektu lub odbiorcy.
7.  Umożliwia wybór kategorii. Zostanie wyświetlona lista kategorii załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, zobacz [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Jeśli Twojej kategorii nie ma na liście, kliknij przycisk **Szukaj**. Wyszukaj według kategorii lub przełącz się do wyszukiwania według nazwy kategorii.
9.  Wybierz działanie. Zostanie wyświetlona lista działań załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, zobacz [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Jeśli Twojego działania nie ma na liście, kliknij przycisk **Szukaj**. Wyszukaj według numeru działania lub przełącz się do wyszukiwania według celu.

11. Wybierz właściwość wiersza.
12. Opcjonalne: Wprowadź komentarze wewnętrzne i zewnętrzne.
13. Wybierz opcję **Gotowe**.

