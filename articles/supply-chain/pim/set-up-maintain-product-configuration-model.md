---
title: Tworzenie modelu konfiguracji produktu
description: W tym artykule opisano kroki tworzenia i konfigurowania modelu konfiguracji produktu.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dd4346f8b2f253721df23fbcff71e3a0e78bb2cc
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-a-product-configuration-model"></a>Tworzenie modelu konfiguracji produktu

[!include[banner](../includes/banner.md)]


W tym artykule opisano kroki tworzenia i konfigurowania modelu konfiguracji produktu.

| Zadanie                                                        | opis                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tworzenie produktu głównego.                                    | Tworzenie produktu głównego z listy **produkt główny**. Zwolnij produkt główny do wszystkich odpowiednich firm. Dla produktu głównego używanego jako wersja modelu konfiguracji produktu lub jako podskładnik należy wybrać opcję **Konfiguracja oparta na ograniczeniach** jako technologię konfiguracji, a wymiar konfiguracji musi być wybrany tylko dla grupy wymiarów produktu. |
| Tworzenie składników.                                          | Tworzenie składników na stronie **Składniki**. Składniki są elementami składowymi modelu konfiguracji produktu i mogą być ponownie użyte w wielu modelach konfiguracji produktu.                                                                                                                                                                                                                      |
| Tworzenie typu atrybutu.                                     | Utwórz typy atrybutów na stronie **Typy atrybutów**. Typy atrybutów określają zestaw typów danych dla atrybutów, które są używane w modelach konfiguracji produktu. Atrybuty typu **Wartość logiczna**, **Tekst** z listą stałą i **Wartość całkowita** z typami zakresów i zestaw wartości, które są dostępne podczas konfigurowania wariantu produktu według modelu konfiguracji produktu.       |
| Tworzenie modelu konfiguracji produktu.                       | Utwórz model konfiguracji produktu na stronie **Nowy model konfiguracji produktu**.                                                                                                                                                                                                                                                                                                              |
| Dodawanie atrybutów do modelu konfiguracji produktu.            | Utwórz atrybut na skróconej karcie **Atrybuty** na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu wybierz atrybut, który będzie używany jako docelowy**. Atrybuty opisują wszystkie funkcje modelu konfiguracji produktu.                                                                                                                                                                                                       |
| Dodawanie ograniczeń do modelu konfiguracji produktu.           | Utwórz ograniczenia na skróconej karcie **Ograniczenia** na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu wybierz atrybut, który będzie używany jako docelowy**. Ograniczenia określają warunki brzegowe, jakie musi spełniać konfiguracja produktu. Ograniczenia są mogą być wyrażeniowe lub powiązane z tabelami.                                                                                                                                 |
| Dodawanie składnika podrzędnego do modelu konfiguracji produktu.         | Utwórz składnik podrzędny na skróconej karcie **Składniki podrzędne** na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu wybierz atrybut, który będzie używany jako docelowy**. Składniki podrzędne są powiązane ze składnikami i są połączone z towarami, które reprezentują składnik podrzędny.                                                                                                                                                                       |
| Dodawanie wymagań użytkownika do modelu konfiguracji produktu.     | Wymagania użytkownika są podobne do składników podrzędnych, ale nie odwołuje się do elementu. Można je traktować jako fantomowy BOM. Wszystkie wiersze BOM lub operacje marszruty znajdujące się bezpośrednio pod wymaganiami użytkownika zostaną zwinięte do składnika nadrzędnego.                                                                                                                       |
| Dodawanie wierszy BOM do modelu konfiguracji produktu.             | Utwórz wiersze BOM na skróconej karcie **Wiersze BOM** na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu wybierz atrybut, który będzie używany jako docelowy**. Wiersze BOM są częścią wymaganą do utworzenia wariantu produktu.                                                                                                                                                                                                 |
| Dodawanie operacji marszruty do modelu konfiguracji produkcji.      | Utwórz operacje marszruty na skróconej karcie **Operacje marszruty** na stronie **Szczegóły modelu konfiguracji produktu opartej na ograniczeniu wybierz atrybut, który będzie używany jako docelowy**. Operacje marszruty są krokiem w sekwencji kroków wykonywanych w celu wykonania wariantu produktu.                                                                                                                                                    |
| Tworzenie aktywnej wersji modelu konfiguracji produktu. | Utwórz aktywną wersję modelu konfiguracji produktu na stronie **Wersje**. Wersja jest relacją między modelem konfiguracji produktu a produktem głównym. Model konfiguracji produktu z aktywną wersją może być skonfigurowany z zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego.                                                               |
| Testowanie modelu konfiguracji produktu.                         | Testowanie modelu konfiguracji produktu albo za strony **Szczegóły modelu konfiguracji produktu opartego na ograniczeniu** albo ze strony **Lista modeli konfiguracji produktu**. Testowanie modeli konfiguracji produktu symuluje proces konfiguracji modelu produktu, który powstaje w trakcie obsługi zamówienia.                                                                                                |
| Tworzenie szablonu modelu konfiguracji produktu.                | Utwórz szablon modelu konfiguracji produktu na stronie **Szablony konfiguracji**. Szablon konfiguracji zawiera wartości atrybutów w modelu konfiguracji produktu. Wybierz wartości atrybutów na stronie **Wiersz konfiguracji**. Można załadować szablon konfiguracji modelu produktu w trakcie konfiguracji modelu produktu.                                                   |
| Konfiguracja towaru.                                          | Model konfiguracji produktu może być skonfigurowany z zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego.                                                                                                                                                                                                                                                                           |






