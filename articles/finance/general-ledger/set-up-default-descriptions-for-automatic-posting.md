---
title: Ustawianie opisów domyślnych dla automatycznego księgowania
description: W tym temacie opisano sposób ustawiania domyślnego tekstu, który opisuje wpisów, które są księgowane automatycznie w księdze głównej. Można skonfigurować domyślny tekst opisu, używając tekstu dowolnego kształtu lub wybrać sztywno określone zmienne.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3963b4ed63021dd3c84a0d87b768486dcb0f386d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837088"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Ustawianie opisów domyślnych dla automatycznego księgowania

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób ustawiania domyślnego tekstu, który opisuje wpisów, które są księgowane automatycznie w księdze głównej. Można skonfigurować domyślny tekst opisu, używając tekstu dowolnego kształtu lub wybrać sztywno określone zmienne.

> [!NOTE]
> W przypadku niektórych typów transakcji w niektórych krajach lub regionach, możesz również uwzględnić tekst z pól w bazie danych Microsoft Dynamics AX, które są związane z tymi rodzajami transakcji. Aby zapoznać się z listą typów transakcji oraz krajami i regionami, zobacz sekcję [Opcjonalnie: Dodaj inny tekst do opisów domyślnych](#optional-add-other-text-to-default-descriptions) w dalszej części tego tematu.

## <a name="set-up-default-descriptions"></a>Ustawianie opisów domyślnych

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Ustawienia** \> **Opisy domyślne**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Opis** wybierz typ transakcji, aby utworzyć domyślny opis.
4. W polu **Język** wybierz język, który ma zostać uwzględniony do opisu.
5. W polu **Tekst** wprowadź opis domyślny. Możesz dowolnie wpisać tekst w polu lub użyć jednej lub więcej z następujących niezależnych zmiennych:

    - **%1** — dodaj datę transakcji.
    - **%2** — dodaj identyfikator, który odnosi się do typu dokumentu, który jest księgowany w księdze głównej. Na przykład w przypadku kopii przeznaczonej dla typów transakcji, które są powiązane z fakturą, zmienna **%2** dodaje numer faktury.
    - **%3**— dodaj identyfikator, który odnosi się do typu dokumentu, który jest księgowany w księdze głównej. Na przykład w przypadku kopii przeznaczonej dla typów transakcji, które są powiązane z fakturą, zmienna **%3** dodaje numer konta odbiorcy.

## <a name="optional-add-other-text-to-default-descriptions"></a>Opcjonalnie: Dodaj inny tekst do opisów domyślnych

W przypadku niektórych typów transakcji w niektórych krajach lub regionach, domyślne opisy moga zawierać tekst pochodzący z pół w twoich danych, które są związane z tymi rodzajami transakcji. Poniższa lista zawiera typy transakcji i kraje oraz regiony, dla których ta opcja jest dostępna.

**Typy transakcji**

Można dodać inny tekst do opisów domyślnych dla typów transakcji, które są powiązane z następującymi typami dokumentów:

- Faktury dla odbiorcy
- Odbiorca faktury korygującej
- Płatność odbiorcy gotówką
- Płatności dostawcy
- Zamówienia sprzedaży
- Zamówienia zakupu
- Arkusze magazynowe
- Planowanie główne (MRP)
- Środki trwałe

**Kraje i regiony**

Ta opcja jest dostępna dla następujących krajów i regionów:

- Brazylia
- Chiny
- Czechy
- Europa Wschodnia
- Węgry
- Indie
- Japonia
- Litwa
- Łotwa
- Polska
- Rosja

### <a name="add-text-to-default-descriptions"></a>Dodaj tekst do opisów domyślnych

Po wykonaniu kroków w procedurze [Ustawianie opisów domyślnych](#set-up-default-descriptions) , opisanej we wcześniejszej sekcji tego tematu, należy wykonać następujące kroki, aby dodać inny tekst do opisu domyślnego.

1. Na skróconej karcie **Parametry** wybierz pozycję **Dodaj**.
2. W polu **Tabela odwołań** zaznacz tabelę bazy danych, z której chcesz dodać do opisu dane parametru.
3. W polu **Pole odwołania** zaznacz pole, z którego chcesz dodać do opisu dane parametru.
4. Powtórz kroki od 1 do 3, aby dodać więcej parametrów.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]