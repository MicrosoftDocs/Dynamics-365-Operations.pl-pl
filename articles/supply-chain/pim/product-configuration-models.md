---
title: Omówienie modeli konfiguracji produktu
description: W tym artykule podano definicje terminów i pojęć, które są istotne dla modeli konfiguracji produktu. Modele konfiguracji produktu pozwalają zbudować standardową strukturę produktu, której potem można używać do konfigurowania wielu wariantów tego samego produktu.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d908b9e58da06646e07ddc5fc4d937cc1f1849cd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563604"
---
# <a name="product-configuration-models-overview"></a>Omówienie modeli konfiguracji produktu

[!include [banner](../includes/banner.md)]

W tym artykule podano definicje terminów i pojęć, które są istotne dla modeli konfiguracji produktu. Modele konfiguracji produktu pozwalają zbudować standardową strukturę produktu, której potem można używać do konfigurowania wielu wariantów tego samego produktu.

Modele konfiguracji produktu są tworzone, aby reprezentować rodzajową strukturę produktu. Po utworzeniu modelu konfiguracji produktu można skonfigurować odrębny wariant produktu, który ma unikalny BOM i marszruty powstawania. W modelach konfiguracji produktów używane są zarówno ograniczenia deklaratywne, jak i obliczenia rozkazujące do obsługi relacji i ograniczeń między różnymi wariantami produktów. Można konfigurować elementy na zamówieniach sprzedaży, ofertach sprzedaży, zamówieniach zakupu i zleceniach produkcyjnych. W poniższej tabeli opisano pojęcia i terminy oparte na ograniczeniach.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Składniki</td>
<td>Składniki są głównymi elementami modelu konfiguracji produktu. Składniki są wyświetlane w postaci struktury drzewa na stronie <strong>Szczegóły modelu konfiguracji produktu</strong>. Składniki mogą zawierać następujące elementy:
<ul>
<li>Atrybuty</li>
<li>Ograniczenia</li>
<li>Obliczenia</li>
<li>Składniki podrzędne</li>
<li>Wymagania użytkownika</li>
<li>Wiersze BOM</li>
<li>Operacje marszruty</li>
</ul></td>
</tr>
<tr class="even">
<td>Atrybuty</td>
<td>Atrybuty opisują wszystkie funkcje modelu konfiguracji produktu. Atrybutów można użyć do określenia funkcji, które można wybrać, gdy skonfigurowano odrębny produkt. Atrybuty są używane w ograniczeniach i warunkach. Gdy atrybuty są tworzone i dodawane do modelu konfiguracji produktu, dołączane są odwołania do powiązanych typów atrybutu. Wartość domyślna może być ustawiona dla atrybutu. Wartość domyślna jest używana w interfejsie użytkownika konfiguracji (UI), gdy model konfiguracji produktu jest konfigurowany. Można określić, że atrybut jest obowiązkowy, tylko do odczytu lub ukryty.
<ul>
<li><strong>Obowiązkowe</strong> — wartość musi być ustawiona dla atrybutu, gdy produkt jest konfigurowany.</li>
<li><strong>Tylko do odczytu</strong> — wartość atrybutu jest wyświetlana podczas sesji konfiguracji, ale nie można jej zmienić.</li>
<li><strong>Ukryty</strong> — wartość atrybutu jest uwzględniona w ograniczeniach i warunkach, ale nie jest wyświetlana podczas sesji konfiguracji.</li>
</ul>
Można również określić warunek dla atrybutów. Jeśli warunek jest spełniony, wartość musi być wprowadzona dla atrybutu obowiązkowego. Warunki są wyrażeniami, które muszą zostać spełnione dla atrybutów, wierszy BOM i operacji marszruty do uwzględnienia w modelu konfiguracji produktu. Każdy atrybut, który odwołuje się do warunku, staje się wymagany. Zalecamy wybranie atrybutów jako obowiązkowych na karcie <strong>Atrybuty</strong>. Ułatwi to identyfikację atrybutów obowiązkowych. Wartość atrybutu są ważną częścią ponownego wykorzystania konfiguracji. System używa wartości atrybutu w celu ustalenia, czy istniejąca konfiguracja pasuje do elementów wybranych przez użytkownika podczas sesji konfiguracji.</td>
</tr>
<tr class="odd">
<td>Typy atrybutów</td>
<td>Typy atrybutu określają zestaw typów danych dla atrybutów, które są używane w modelu konfiguracji produktu. Następujące typy atrybutów są używane:
<ul>
<li><strong>Liczba całkowita</strong> z zakresem lub bez</li>
<li><strong>Dziesiętne</strong></li>
<li><strong>Tekst</strong> ze stałą listą lub bez</li>
<li><strong>Wartość logiczna</strong></li>
</ul>
Jeśli typem atrybutu jest <strong>Wartość logiczna</strong>, <strong>Liczba całkowita</strong> z zakresem lub <strong>Tekst</strong> ze stałą listą, zbiór wartości jest dostępny podczas ustawiania modelu konfiguracji produktu. <strong>Uwaga:</strong> Narzędzie do rozwiązywania problemów z konfiguracją produktu rozpoznaje tylko następujące typy atrybutów: <strong>Wartość logiczna</strong>, <strong>Tekst</strong> ze stałą listą i <strong>Liczba całkowita</strong> z zakresem. Dzięki temu można używać tylko tych typów atrybutów w ograniczeniach i warunkach wyrażeniowych.</td>
</tr>
<tr class="even">
<td>Ograniczenia</td>
<td>Ograniczenia opisują ograniczenia dla konfiguracji modelu produktu. Ograniczenia mają zagwarantować, że będą wybrane tylko prawidłowe wartości, gdy produkt jest konfigurowany. Ograniczenia mogą być ograniczeniami wyrażeniowymi lub powiązanymi tabelami:
<ul>
<li>Ograniczenie wyrażenia może służyć tylko do składnika, który jest powiązany. Ograniczenia wyrażenia dla składnika mogą odwoływać się do atrybutów składników podrzędnych dla składników. Narzędzie do rozwiązywania problemów z konfiguracją produktu jest używane w celu rozwiązania ograniczeń, a użytkownik musi używać jego składni podczas zapisywania ograniczeń. Więcej informacji można uzyskać w temacie o ograniczeniach wyrażeń i tabel.</li>
<li>Przed zastosowaniem ograniczeń tabel do składnika w modelu konfiguracji produktu takie ograniczenia muszą zostać zdefiniowane. Ograniczenia tabel mogą być definiowane albo przez użytkownika, albo przez system. Powiązane tabele zdefiniowane przez użytkownika to typ macierzy, który może być używany do opisywania zestawu kombinacji dla wartości atrybutów, które są zdefiniowane przez typy atrybutu. Na przykład w przypadku produkcji głośników, macierz dla powiązanych tabel zdefiniowanych przez użytkownika może mieć kolumny dla wykończenia i maskownice głośnika.</li>
</ul>
<strong>Przykład</strong> Głośniki są dostępne cztery wykończeniach: Czarny, Dąb, Rosewood i Biały. Głośniki mogą mieć jeden z trzech rodzajów maskownicy: Czarny, Metal lub Biały. Białe wykończenie jest dostępne dla wszystkich maskownic, ale w przypadku innych wykończeń obowiązują ograniczenia. W poniższej tabeli przedstawiono przykład informacji wyświetlanych na karcie <strong>Dozwolone kombinacje</strong> na stronie <strong>Edytuj ograniczenie tabeli</strong>.
<table>
<thead>
<tr class="header">
<th>Wykończenie</th>
<th>Maskownica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Czarny</td>
<td>Czarny</td>
</tr>
<tr class="even">
<td>Czarny</td>
<td>Metal</td>
</tr>
<tr class="odd">
<td>Czarny</td>
<td>Biały</td>
</tr>
<tr class="even">
<td>Dąb</td>
<td>Czarny</td>
</tr>
<tr class="odd">
<td>Rosewood</td>
<td>Biały</td>
</tr>
<tr class="even">
<td>Biały</td>
<td>Czarny</td>
</tr>
<tr class="odd">
<td>Biały</td>
<td>Biały</td>
</tr>
</tbody>
</table>
Powiązane tabele zdefiniowane przez system reprezentują mapowanie między typem atrybutu i polem w tabeli programu Finance and Operations. Ograniczenie tabeli zdefiniowane przez system dynamicznie łączy typ atrybutu z polem. Dzięki temu połączeniu atrybut w modelu konfiguracji produktu może odzwierciedlać dane widoczne w polu w tabeli programu Finance and Operations.</td>
</tr>
<tr class="odd">
<td>Obliczenia</td>
<td>Obliczenia są dodatkiem do ograniczeń. Można ich używać do wykonywania operacji arytmetycznych na atrybutach typu <strong>Liczba dziesiętna</strong> i <strong>Liczba całkowita</strong> lub operacji logicznych, które obejmują atrybuty typu <strong>Tekst</strong> ze stałą listą i <strong>Wartość logiczna</strong>. Obliczenie ma atrybut docelowy, który będzie zawierał wynik wyrażenia do obliczeń. Wyrażenie do obliczania opiera się na edytorze wyrażeń.</td>
</tr>
<tr class="even">
<td>Składniki podrzędne</td>
<td>Składniki podrzędne odzwierciedlają strukturę drzewa modelu konfiguracji produktu. Można używać składników podrzędnych, aby konstruować strukturę modelu konfiguracji produktu. Składniki podrzędne odnoszą się do istniejących składników. W związku z tym za pomocą składników podrzędnych zachęca się do ponownego używania składników w wielu modelach konfiguracji produktu. Na stronie <strong>Szczegóły wiersza BOM</strong> dla wybranego składnika podrzędnego można wybrać dla odrębną wartość. Ewentualnie można wybrać atrybut, dla którego wartość jest wybierana podczas ustawiania modelu konfiguracji produktu. Aby uwzględnić produkt jako składnik lub składnik podrzędny, podczas tworzenia produktu trzeba określić następujące informacje na stronie<strong> Tworzenie produktów</strong>:
<ul>
<li>W polu <strong>Typ produktu</strong> wybierz <strong>Towar</strong>.</li>
<li>W polu <strong>Podtyp produktu</strong> wybierz <strong>Produkt główny</strong>.</li>
<li>W polu <strong>Technologia konfiguracji</strong> wybierz <strong>Konfiguracja oparta na ograniczeniach</strong>.</li>
</ul>
Można wyświetlić, czy zwolniony produkt może być używany jako składnik lub składnik podrzędny na karcie <strong>Ogólne</strong> na stronie <strong>Szczegóły zwolnionego produktu</strong>. Jeśli wybrano opcję <strong>Konfiguracja oparta na ograniczeniach</strong> w polu <strong>Technologia konfiguracji</strong>, produkt może być używany jako składnik lub składnik podrzędny. Można ukryć podskładniki, tak że nie są one wyświetlane użytkownikowi podczas sesji konfiguracji. Atrybuty, podskładniki i wymagania użytkowników, które są związane z podskładnikiem, również będą ukryte.</td>
</tr>
<tr class="odd">
<td>Wymagania użytkownika</td>
<td>Wymagania użytkownika reprezentują abstrakcję między wymaganiami użytkownika i określonymi składnikami oraz atrybutami. Nie można mapować wymagania użytkownika na towar. Na przykład odbiorca dokonuje zakupu systemu kina domowego. Przedstawiciel handlowy może zadawać pytania o wielkość pokoju, w którym odbiorca planuje zainstalować system, aby określić, ile watów będzie potrzebował. W tym przykładzie wielkość pomieszczenia może być wymaganiem użytkownika, które pomoże określić odpowiednią wartość atrybutu dla określonego składnika. Można ukryć wymagania użytkownika, tak że nie są one wyświetlane użytkownikowi podczas sesji konfiguracji. Atrybuty, podskładniki i wymagania użytkowników, które są związane z wymaganiem użytkownika, również będą ukryte. Można zapisać warunek, aby sterować tym, czy wymaganie użytkownika może być ukryte. Trzeba zapisać warunek za pomocą składni Optimization Modeling Language (OML).</td>
</tr>
<tr class="even">
<td>Wiersze BOM</td>
<td>Wiersze BOM reprezentują poszczególne materiały składników w modelu konfiguracji produktu. Na stronie <strong>Szczegóły wiersza BOM</strong> wszystkie elementy są dostępne do wyboru. Warunek można dodać do wiersza BOM, co spowoduje, że wiersze BOM, które wybrano do odrębnego produktu wariantu, mogą zmieniać odpowiednio do wyboru użytkownika, gdy tworzony jest model konfiguracji produktu. Warunki są wyrażeniami, które muszą zostać spełnione dla atrybutów, wierszy BOM i operacji marszruty do uwzględnienia w modelu konfiguracji produktu. Na stronie <strong>Szczegóły wiersza BOM</strong> można wybrać odrębną wartość. Ewentualnie można mapować na atrybut, dla którego wartość jest wybierana podczas tworzenia modelu konfiguracji produktu.</td>
</tr>
<tr class="odd">
<td>Operacje marszruty</td>
<td>Na stronie <strong>Szczegóły operacji marszruty</strong> można wybrać odrębną wartość. Ewentualnie można mapować na atrybut, dla którego wartość jest wybierana podczas tworzenia modelu konfiguracji produktu. Warunki są zapisane jak ograniczenia wyrażenia. Warunki są wyrażeniami, które muszą zostać spełnione dla atrybutów, wierszy BOM i operacji marszruty do uwzględnienia w modelu konfiguracji produktu.</td>
</tr>
</tbody>
</table>





