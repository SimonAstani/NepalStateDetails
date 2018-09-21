# NepalStateDetails
This fixtures gives state wise details of municipality, sub-municipality,   District. Especially build for django fixtures..
and stores into the corresponding models..
The models details are:
```
class Country(models.Model):
    name = models.CharField(max_length=254)


class State(models.Model):
    name = models.CharField(max_length=254)
    country = models.ForeignKey(Country)


class District(models.Model):
    name = models.CharField(max_length=254)
    state = models.ForeignKey(State)


class Municipality(models.Model):
    name = models.CharField(max_length=254)
    district = models.ForeignKey(District, related_name='municipality')


class Ward(models.Model):
    number = models.IntegerField()
    municipality = models.ForeignKey(Municipality)```

