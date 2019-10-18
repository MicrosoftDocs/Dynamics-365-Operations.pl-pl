---
title: Konfigurowanie nazw pól aplikacji w aplikacji Magazynowanie
description: W tym temacie opisano sposób definiowania i konfigurowania nazw i priorytetów pól aplikacji magazynowej w usłudze Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a3251368e92eb2e24eb9e64bb615027d038ff660
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251092"
---
# <a name="configure-app-field-names-in-warehousing-app"></a>Konfigurowanie nazw pól aplikacji w aplikacji Magazynowanie

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób definiowania i konfigurowania nazw i priorytetów pól aplikacji magazynowej w usłudze Dynamics 365 Supply Chain Management. 

**Uwaga:** Ten temat dotyczy funkcji w module Zarządzanie magazynem. Nie ma zastosowania do funkcji w module Zarządzanie zapasami. Magazynowanie to aplikacja umożliwiająca wykonywanie zadań magazynowych. Można zdefiniować i skonfigurować nazwy pól używanych w aplikacji, a także skonfigurować priorytety, do których te nazwy pól powinny być przypisane. W tym temacie wyjaśniono sposób definiowania i konfigurowania nazw i priorytetów tych pól aplikacji magazynowej oraz ich używanie w aplikacji Magazynowanie. Aby uzyskać szczegółowe informacje dotyczące konfigurowania połączenia z aplikacją Magazynowanie, skorzystaj z samouczka [Instalowanie i konfigurowanie aplikacji Magazynowanie](install-configure-warehousing-app.md).

## <a name="configure-warehouse-app-field-names"></a>Konfigurowanie nazw pól w aplikacji magazynowej

Gdy używasz aplikacji Magazynowanie na urządzeniu mobilnym, można na stronie **Nazwy pól w aplikacji Magazynowanie** skonfigurować sposób wyświetlania metadanych na urządzeniu. W nowej firmie wybierz opcję **Utwórz konfigurację domyślną**, aby wygenerować wszystkie nazwy pól, które będą używane w przepływach pracy magazynu na urządzeniu, a następnie przypisz do nich preferowany tryb wprowadzania i typ danych wejściowych. Po wygenerowaniu wszystkich nazw pól można wybrać następujące opcje wprowadzania danych:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opcja</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Preferowany tryb wprowadzania</td>
<td>Ta opcja określa, czy dla wybranej nazwy pola ma być wyświetlane pole wprowadzania danych przez skanowania, czy przez ręczne wpisywanie. Rozróżnianie pól jest przydatne, jeśli dla pola są używane kody kreskowe. <strong>Uwaga:</strong> Dla nazw pól o preferowanym trybie wprowadzania <strong>Skanowanie</strong> można wprowadzać dane ręcznie, jeśli kod kreskowy jest uszkodzony lub nieczytelny.</td>
</tr>
<tr class="even">
<td>Typ danych wejściowych</td>
<td>Ta opcja określa, który tryb wprowadzania powinien być stosowany do wybranej nazwy pola. Dostępne są cztery opcje:
<ul>
<li><strong>Wybór</strong> - Zawiera listę opcji do wyboru. Nazwy pól z tą opcją nie mogą być edytowane.</li>
<li><strong>Data</strong> - Nazwy pól określone jako daty będą pokazywały format daty z etykietą. Dzięki temu pracownicy magazynu łatwiej widzą, w jakim formacie należy wpisać datę. Nazwy pól z tą opcją nie mogą być edytowane.</li>
<li><strong>Alfa</strong> - Gdy wybierzesz tę opcję, podczas ręcznego wprowadzania informacji w aplikacji będzie używana klawiatury urządzenia. Zachowanie klawiatury można zmieniać w zależności od wykorzystywanego urządzenia.</li>
<li><strong>Numeryczna</strong> - Dla nazw pól wykorzystujących tylko numeryczne dane wejściowe można wybrać tę opcję, a zamiast klawiatury urządzenia będzie wyświetlana niestandardowa klawiatura numeryczna z polem wprowadzania.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>Konfigurowanie priorytetu pól w aplikacji magazynowej

Na stronie **Priorytet pola w aplikacji magazynowej** można umieścić nazwy pól w różnych grupach priorytetu. Dzięki temu można zdecydować, które informacje mają być wyświetlane na głównej stronie zadań, gdy pracownicy magazynu wykonują zadania za pomocą aplikacji. Jeśli klikniesz opcję **Utwórz konfigurację domyślną**, zostanie wygenerowany domyślny zestaw grup priorytetu. Można utworzyć dowolną potrzebną liczbę grup priorytetu, ale tylko trzy będą wyświetlane na stronie zadania. Gdy system wysyła metadane do aplikacji, przypisuje każdemu polu względny priorytet w zależności od jego grupy priorytetu, a aplikacja wyświetla na stronie zadania pierwsze trzy grupy priorytetu zawarte w metadanych. Pozostała zawartość metadanych będzie wyświetlana na pomocniczej stronie szczegółów. Poniższa tabela pokazuje przykład pięciu grup priorytetu.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupa priorytetu</th>
<th>Przypisane pola</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Priorytet 10</td>
<td><ul>
<li>Element</li>
<li>Ilość</li>
<li>Jednostka miary</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorytet 20</td>
<td><ul>
<li>Stanowisko w grupie</li>
<li>Grupa</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorytet 30</td>
<td><ul>
<li>Opis towaru</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorytet 40</td>
<td><ul>
<li>Konfiguracja</li>
<li>Kolor</li>
<li>Rozmiar</li>
<li>Styl</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorytet 50</td>
<td><ul>
<li>Lokalizacja</li>
<li>Numer identyfikacyjny</li>
</ul></td>
</tr>
</tbody>
</table>

Na przykład gdy pracownik magazynu wykonuje zadanie na urządzeniu przenośnym, a metadane, które będą wyświetlane w aplikacji, składają się z następujących pól:

-   Element
-   Ilość
-   Jednostka miary
-   Opis towaru
-   Rozmiar i lokalizacja

Na podstawie priorytetu pól aplikacji magazynowej skonfigurowanego w tabeli powyżej następujące 3 wiersze informacji będą wyświetlane na stronie zadania:

-   Wiersz 1: Towar, Ilość, Jednostka miary
-   Wiersz 2: Opis towaru
-   Wiersz 3: Rozmiar

Pozostałe metadane, na przykład Lokalizacja, nie będą wyświetlane na stronie zadania, ale będą wyświetlane na stronie szczegółów. Aby dowiedzieć się więcej i zobaczyć przykłady interfejsu użytkownika, należy się zapoznać z wpisem na blogu [Zapowiedź aplikacji Finance and Operations — Magazynowanie](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Instalowanie i konfigurowanie Microsoft Dynamics 365 for Finance and Operations — magazynowanie](install-configure-warehousing-app.md)
