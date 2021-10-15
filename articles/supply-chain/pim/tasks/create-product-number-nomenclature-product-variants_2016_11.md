---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu
description: Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7711d9832288327e700acd47fb30cce0c76e5e9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568406"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym. W procedurze zademonstrowano również, jak zbudować konwencję nazewnictwa konfiguracji dla składnika modelu konfiguracji produktu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Nowa konwencja nazewnictwa numerów produktu jest przypisana do produktu głównego D0004. Zazwyczaj zadanie wykonuje projektant produktów.

## <a name="create-a-product-number-nomenclature"></a>Tworzenie konwencji nazewnictwa numerów produktu

1. Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Ustawienia \> Nazewnictwo produktów**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Opis** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Numer produktu głównego**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Konfiguracja**.
1. Zamknij stronę.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Przypisywanie konwencji nazewnictwa numerów produktu do produktu głównego

1. Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.
1. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład ustaw filtr na pole **Numer produktu** z wartością „D”.
1. Na liście wybierz łącze w wybranym wierszu.
1. Wybierz opcję **Edycja**.
1. W polu **Użyj nazewnictwa** zaznacz opcję *Tak*.
1. W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.
1. Zamknij stronę.
1. Zamknij stronę.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Tworzenie konwencji nazewnictwa dla składnika modelu konfiguracji produktu

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. Wybierz opcję **Edycja**.
1. W polu **Użyj nazewnictwa konfiguracji** wybierz opcję *Tak*.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Wartość atrybutu**.
1. Na liście oznacz wybrany wiersz.
1. Wprowadź lub wybierz wartość w polu **Atrybut**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Wartość atrybutu**.
1. Na liście oznacz wybrany wiersz.
1. Wprowadź lub wybierz wartość w polu **Atrybut**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Wartość atrybutu**.
1. Na liście oznacz wybrany wiersz.
1. Wprowadź lub wybierz wartość w polu **Atrybut**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Wartość atrybutu**.
1. Na liście oznacz wybrany wiersz.
1. Wprowadź lub wybierz wartość w polu **Atrybut**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz opcję **Wartość sekwencji numerów**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Sekwencja numerów** wprowadź lub wybierz wartość.
1. Zamknij stronę.
1. Zamknij stronę.
1. Zamknij stronę.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]