---
title: "Tworzenie atrybutów i zarządzanie nimi"
description: "Ten artykuł opisuje atrybuty dostępne w programie Microsoft Dynamics 365 for Operations. Atrybuty pozwalają opisać produkt i jego charakterystykę w polach definiowanych przez użytkownika."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 26c628e10aaa5f47bc87d7510ca8f41ab3630204
ms.lasthandoff: 03/31/2017


---

# <a name="create-and-manage-attributes"></a>Tworzenie atrybutów i zarządzanie nimi

Ten artykuł opisuje atrybuty dostępne w programie Microsoft Dynamics 365 for Operations. Atrybuty pozwalają opisać produkt i jego charakterystykę w polach definiowanych przez użytkownika.

Atrybuty pozwalają opisać produkt i jego charakterystykę w polach definiowanych przez użytkownika. Można na przykład określić rozmiar pamięci produktu i pojemność dysku twardego oraz wskazać, czy produkt jest zgodny z normą poboru mocy. Atrybuty można skojarzyć z różnymi jednostkami sprzedaży detalicznej, takimi jak kategorie produktu i kanały handlu detalicznego oraz ustawić ich wartości domyślne. Produkty dziedziczą atrybuty i wartości domyślne dla tych atrybutów, gdy zostaną powiązane z kategoriami produktów lub kanałami sprzedaży detalicznej. Wartości domyślne można zastąpić na poziomie poszczególnych produktów na poziomie kanału sprzedaży detalicznej lub w katalogu sieci sprzedaży.

#### <a name="examples"></a>Przykłady

Kategoria

Atrybut

Możliwe wartości

Wartość domyślna

Telewizja i wideo

Marka

Dowolna prawidłowa wartość **marki**

Brak

TELEWIZJA

Rozmiar ekranu

**20"**–**80"**

Brak

Rozdzielczość w pionie

**480i**, **720p**, **1080i**, lub **1080p**

**1080p**

Częstotliwość odświeżania ekranu

**60hz**, **120hz**, lub **240hz**

**60hz**

Wejścia HDMI

**0**–**10**

**3**

Wejścia DVI

**0**–**10**

**1**

Wejście kompozytowe

**0**–**10**

**2**

Wejścia komponentów

**0**–**10**

**1**

LCD

3D Ready

**Tak** lub **Nie**

**Tak**

Obsługa 3D

**Tak** lub **Nie**

**Nie**

Plazmowy

Minimalna temperatura

**32**–**110** stopni

**32**

Maksymalna temperatura

**32**–**110** stopni

**100**

Projekcyjny

Gwarancja na lampę kineskopową

**6**, **12** lub **18** miesięcy

**12**

\# lamp kineskopowych

**1**–**5**

**3**

## <a name="attribute-type"></a>Typ atrybutu
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) Atrybuty są oparte na typach atrybutów. Typ atrybutu określa typ danych, które można wprowadzić dla określonego atrybutu. Obecnie program Microsoft Dynamics 365 for Operations obsługuje następujące typy atrybutów:

-   **Waluta** — ten typ atrybutu obsługuje wartości waluty. Może być ograniczona (czyli obsługuje zakres wartości), lub może pozostać otwarta.
-   **Data i godzina** — ten typ atrybutu obsługuje wartości daty i godziny. Może być ograniczona (czyli obsługuje zakres wartości), lub może pozostać otwarta.
-   **Dziesiętna** — ten typ atrybutu obsługuje wartości liczbowe, które zawierają miejsca dziesiętne. Obsługuje ona również jednostki miary. Może być ograniczona (czyli obsługuje zakres wartości), lub może pozostać otwarta.
-   **Całkowita** — ten typ atrybutu obsługuje wartości numeryczne. Obsługuje ona również jednostki miary. Może być ograniczona (czyli obsługuje zakres wartości), lub może pozostać otwarta.
-   **Tekst** — ten typ atrybutu obsługuje wartości tekstowe. Obsługuje ona również wstępnie zdefiniowany zestaw możliwych wartości (wyliczenia).
-   **Logiczna** — ten typ atrybutu obsługuje wartości binarne (**prawda**/**fałsz**).
-   **Odwołanie**.

## <a name="attribute"></a>Atrybut
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Oprócz nazwy, przyjaznej nazwy, opisu i tekstu Pomocy, w atrybucie można też umieścić jedną lub więcej z poniższych informacji:

-   Wartość domyślna
-   Metadane atrybutu, takie jak metadane wskazujące, czy atrybut można wyszukiwać, modyfikować lub sortować

## <a name="attribute-group"></a>Grupa atrybutów
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Po zdefiniowaniu atrybutów można je podzielić na grupy atrybutów. Grupy atrybutów zawierają grupy odnoszące się do poszczególnych atrybutów i można je przypisać do kategorii lub kanałów sieci sprzedaży.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Przypisywanie grup atrybutów do kategorii sieci sprzedaży
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) Można skojarzyć jedną lub kilka grup atrybutów z węzłami hierarchii kategorii produktów sieci sprzedaży. Gdy produkty zostały skategoryzowane, dziedziczą atrybuty, które są włączone do grup atrybutów.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Przypisywanie grup atrybutów do kategorii sklepów sieci sprzedaży
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) Można skojarzyć jedną lub kilka grup atrybutów z co najmniej jednym sklepem sieci sprzedaży w hierarchii sklepów sieci sprzedaży. Gdy produkty zostały uwzględnione w określonych sklepach sieci sprzedaży, dziedziczą atrybuty, które są włączone do grup atrybutów.

## <a name="overriding-attribute-values"></a>Zastępowanie wartości atrybutów
### <a name="at-the-product-level"></a>Na poziomie produktu

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Wartości domyślne atrybutów można zastąpić na poziomie produktu (tzn. poszczególnych produktów).

### <a name="in-a-retail-catalog"></a>W katalogu sieci sprzedaży

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Dla poszczególnych produktów można zastąpić domyślne wartości atrybutów w określonych katalogach kierowanych do konkretnych kanałów sprzedaży detalicznej.

### <a name="at-the-retail-channel-level"></a>Na poziomie kanału sprzedaży detalicznej

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Dla poszczególnych produktów można zastąpić domyślne wartości atrybutów w określonych katalogach kierowanych do konkretnych kanałów sprzedaży detalicznej.


