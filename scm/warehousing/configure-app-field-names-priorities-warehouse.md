---
title: "Konfigurowanie nazwy pól aplikacji w aplikacji magazynowanie"
description: "W tym temacie opisano sposób definiowania i skonfigurować Magazyn aplikacji pola nazwy i priorytety w usłudze Dynamics 365 dla operacji."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Konfigurowanie nazwy pól aplikacji w aplikacji magazynowanie

W tym temacie opisano sposób definiowania i skonfigurować Magazyn aplikacji pola nazwy i priorytety w usłudze Dynamics 365 dla operacji. 

**Uwaga:** ten temat dotyczy funkcji w module Zarządzanie magazynem. Nie ma zastosowania do funkcji w module Zarządzanie zapasami. Dynamics 365 dla operacji - składu jest aplikacją, która służy do wykonywania zadań hurtowni. Użytkownik może zdefiniować i skonfigurować nazwy pól, które są używane w aplikacji, a także skonfigurować priorytet, do którego powinny być przypisane nazwy pól. W tym temacie wyjaśniono, jak zdefiniować i skonfigurować te nazwy pól aplikacji magazynu i priorytetów i jak są używane w usłudze Dynamics 365 dla operacji - składu. Aby uzyskać szczegółowe informacje dotyczące konfigurowania połączenia do 365 Dynamics dla operacji - składowania, skorzystaj z samouczka [zainstalować i skonfigurować usługi Dynamics 365 dla operacji - składu](install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Konfigurowanie nazwy pól aplikacji magazynu
===================================

Przy użyciu Dynamics 365 dla operacji - magazynowania na urządzeniu przenośnym, można skonfigurować wyświetlanie metadanych na urządzeniu na **magazyn, nazwy pól aplikacji** strony. W nowej firmy w usłudze Dynamics 365 dla operacji, zaznacz **Utwórz domyślne ustawienia** do generowania wszystkich nazw pól, które będą używane w przepływach pracy urządzenia przenośnego magazynu, a następnie przypisz do nich preferowany tryb wprowadzania i typ danych wejściowych. Po wygenerowaniu wszystkich nazw pól, można wybrać następujące opcje wprowadzania.

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
<td>Opcja ta określa, czy pole skanowania lub ręcznego wprowadzania pole wejściowe powinien być wyświetlany dla nazwy zaznaczonego pola. Jest to przydatne do rozróżniania pól w zależności od tego, jeśli używane są kody kreskowe dla pola. <strong>Uwaga:</strong> dla nazwy pól z preferowany tryb wprowadzania jest ustawiona na <strong>skanowanie</strong>, można wprowadzić dane ręcznie, jeśli kod kreskowy jest uszkodzony lub nieczytelny.</td>
</tr>
<tr class="even">
<td>Typ danych wejściowych</td>
<td>Opcja ta definiuje wejściowego typu stosuje się dla wybranego pola Nazwa. Dostępne są cztery opcje:
<ul>
<li><strong>Wybór</strong> - zawiera listę opcji do wyboru. Nazwy pól z tej opcji nie są edytowalne.</li>
<li><strong>Data</strong> - określony jako data pokaże format daty z etykietą nazw pól. Pomaga to zobaczyć w którym formacie należy wprowadzić datę pracowników magazynu. Nazwy pól z tej opcji nie są edytowalne.</li>
<li><strong>Alfa</strong> - po zaznaczeniu klawiatury urządzenia będą używane podczas ręcznego wprowadzania informacji w aplikacji. Doświadczenie klawiatury można zmieniać w zależności od tego, które urządzenie jest używane.</li>
<li><strong>Liczbowe</strong> - dla tego numeryczne użycia tylko odbiór nazwy pól, można wybrać tę opcję, aby wyświetlić niestandardowe numerycznej z pole wprowadzania zamiast klawiatury urządzenia.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Konfigurowanie priorytetu pole aplikacji magazynu
======================================

Na **Magazyn aplikacji pole Priorytet** stronę, nazwy pól można umieścić w grupach różne priorytety. Dzięki temu można wybrać, jakie informacje mają być wyświetlane na stronie głównej zadania po pracowników magazynu wykonywanie zadań za pomocą aplikacji. Jeśli klikniesz **Utwórz domyślne ustawienia**, zostanie wygenerowany zestaw domyślny priorytet grup. Można utworzyć dowolną liczbę grup priorytetowych, w razie potrzeby, ale tylko trzy grupy priorytet pojawi się na stronie zadania. Przy 365 Dynamics dla operacji wysyła metadanych do aplikacji, będzie przypisanie każdego pola priorytet względny w zależności od jego grupa priorytet, a aplikacja wyświetli pierwszych trzech priorytet grup zawarte w metadanych na stronie zadania. Pozostałe brzegi metadanych pojawi się na stronie szczegółów pomocniczego. Poniższa tabela zawiera przykład pięć grup priorytetowych.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Priorytet grupy</th>
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

Na przykład, kiedy pracownik magazynu jest wykonywanie zadań na urządzeniu przenośnym, jeśli metadanych, które będą wyświetlane w aplikacji składa się z następujących pól:

-   Element
-   Ilość
-   Jednostka miary
-   Opis towaru
-   Rozmiar i położenie

Na podstawie magazynu aplikacji pola priorytetu w powyższej tabeli, następujące 3 wierszy zawierających informacje będą wyświetlane na stronie zadania:

-   Rząd 1: Towaru, ilość, jednostka miary
-   Wiersza 2: Opis towaru
-   Rząd 3A: rozmiar

Pozostałe metadane, na przykład lokalizacji, nie będą wyświetlane na stronie zadania, ale będą wyświetlane na stronie Szczegóły. Aby dowiedzieć się więcej i zobacz przykłady interfejsu użytkownika, należy zapoznać się z blogu [ogłaszając 365 Dynamics dla operacji - składu](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Informacje dodatkowe
--------

[Instalowanie i konfigurowanie usługi Microsoft Dynamics 365 dla operacji – składu](install-configure-warehousing-app.md)


