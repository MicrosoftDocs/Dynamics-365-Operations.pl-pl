---
title: Raportowanie finansowe
description: Funkcjonalność raportowania finansowego pozwala specjalistom finansowym i biznesowym tworzyć, obsługiwać, wdrażać i wyświetlać sprawozdania finansowe. Wychodzi poza tradycyjne ograniczenia sprawozdawczości, pomagając efektywne projektować różne rodzaje raportów.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cdfa9ed24d0456d9beaec03ebac89098131d0675
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771149"
---
# <a name="financial-reporting"></a>Raportowanie finansowe

[!include [banner](../includes/banner.md)]

Funkcjonalność raportowania finansowego w aplikacji pozwala specjalistom finansowym i biznesowym tworzyć, obsługiwać, wdrażać i wyświetlać sprawozdania finansowe. Wychodzi poza tradycyjne ograniczenia sprawozdawczości, pomagając efektywne projektować różne rodzaje raportów.

Funkcjonalność sprawozdawczości finansowej obejmuje obsługę wymiarów. W związku z tym segmenty i wymiary kont są od razu dostępne. Nie są wymagane żadne dodatkowe narzędzia ani czynności konfiguracyjnych.

## <a name="financial-reporting-setup"></a>Ustawienia raportowania finansowego
Strona **Ustawienia raportowania finansowego** zawiera listę wszystkich wymiarów finansowych w systemie. **Księga główna** \> **Ustawienia księgi** \> **Ustawienia raportowania finansowego**.

Strona **Ustawienia raportowania finansowego** zawiera dwie sekcje, które określają dane uwzględniane w raportowaniu finansowym:

- **Karta Wymiary** — różne firmy korzystają z różnych wymiarów i struktur kont, dlatego nie da się określić, w jakiej kolejności użytkownicy będą chwili wyświetlać wszystkie wymiary finansowe w raportach. Na tej stronie można ustawić kolejność wyświetlania wymiarów finansowych podczas tworzenia i wyświetlania raportu w module Raportowanie finansowe.
- **Karta Atrybuty** pozwala wybrać, czy kategorie **Dostawcy** i **Odbiorcy** mają być dostępne podczas filtrowania i projektowania raportów. Raportowanie według dostawcy i odbiorcy będzie przydatne tylko wówczas, jeśli podczas księgowania transakcji nie doda się wielu dostawców lub odbiorców. Wybranie atrybutu Dostawca i/lub Odbiorca wydłuży czas integracji.

## <a name="financial-reporting-components"></a>Składniki raportowania finansowego
Następujące składniki aparatu sprawozdawczości finansowej zapewniają łatwe tworzenie, wyświetlanie i planowanie raportów.

| Składnik        | Funkcje | Informacje dodatkowe |
|------------------|-----------|------------------------|
| Projektant raportów  | Tworzenie bloków konstrukcyjnych raportów, które można łączyć w celu definiowania i generowania raportów. Kreator raportów prowadzi mniej doświadczonych użytkowników przez proces projektowania. Użytkownicy zaawansowani mogą tworzyć nowe bloki konstrukcyjne raportów lub modyfikować istniejące bloki zgodnie z własnymi wymaganiami. | |
| Harmonogramy raportu | Planowanie regularnego generowania jednego raportu lub grupy raportów. | [Generowanie raportów finansowych](generate-financial-report.md) |

## <a name="features"></a>Cechy i funkcje
<table>
<thead>
<tr>
<th>Funkcja</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Elastyczność projektowania raportu</td>
<td>Projektant raportów oferuje następujące opcje raportowania podczas projektowania raportu:
<ul>
<li>Zapisywanie kombinacji wymiarów i ich ponowne wykorzystywanie dla wielu raportów.</li>
<li>Kontrolowanie sposobu formatowania i wyświetlania opisów wymiarów.</li>
<li>Identyfikowanie kont lub wymiarów, które zostały pominięte w elementach podstawowych raportu.</li>
<li>Format nagłówków dla prognoz kroczących.</li>
</ul>
</td>
</tr>
<tr>
<td>Współpraca dotycząca raportu finansowego</td>
<td>Następujące funkcje pomagają w zarządzaniu wytwarzaniem i dystrybucją raportów:
<ul>
<li>Planowanie raportów, tak aby były generowane automatycznie codziennie, co tydzień, co miesiąc lub co rok.</li>
<li>Eksportowanie do formatu XPS tylko do odczytu, który zapewnia lepsze zabezpieczenie dokumentu poprzez używanie podpisów cyfrowych.</li>
<li>Eksportuj do arkusza programu Microsoft Excel.</li>
<li>Aby udostępnić raporty, można utworzyć wiadomości e-mail zawierające łącza do raportów.</li>
</ul>
</td>
</tr>
<tr>
<td>Wyświetlanie interaktywnego raportu</td>
<td>Funkcje interaktywne pozwalają wykonać następujące zadania:
<ul>
<li>Zmiana daty przeglądanego raportu.</li>
<li>Zmiana waluty przeglądanego raportu.</li>
<li>Wyświetlanie raportu w widoku podsumowania lub szczegółów.</li>
<li>Dodawanie filtrów wymiarów w celu ograniczenia zawartość raportu do określonego wymiaru lub kombinacji wymiarów.</li>
<li>Dodawanie filtrów atrybutów w celu ograniczenia zawartość raportu do określonego atrybutu lub kombinacji atrybutów.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Dodatkowe zasoby
[Generowanie raportów finansowych](generate-financial-report.md)
