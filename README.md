# BOSH Release for kafka

## Table of Contents
* [Usage](#usage)
* [Override security groups](#security)
* [Releases](#releases)
<br />
<br />


### <a name="usage"></a>Usage

To use this bosh release, first upload it to your bosh:

```
bosh target BOSH_HOST
git clone ssh://git@stash.hybris.com:7999/idefix/bosh-release-kafka.git
cd bosh-release-kafka
bosh upload release releases/kafka-hybris-1.yml
```

For [bosh-lite](https://github.com/cloudfoundry/bosh-lite), you can quickly create a deployment manifest & deploy a cluster:

```
templates/make_manifest warden
bosh -n deploy
```

For AWS EC2, create a single VM:

```
templates/make_manifest aws-ec2
bosh -n deploy
```

### <a name="security"></a>Override security groups

For AWS & Openstack, the default deployment assumes there is a `default` security group. If you wish to use a different security group(s) then you can pass in additional configuration when running `make_manifest` above.

Create a file `my-networking.yml`:

``` yaml
---
networks:
  - name: kafka1
    type: dynamic
    cloud_properties:
      security_groups:
        - kafka
```

Where `- kafka` means you wish to use an existing security group called `kafka`.

You now suffix this file path to the `make_manifest` command:

```
templates/make_manifest aws-ec2 my-networking.yml
bosh -n deploy
```

### <a name="releases"></a>Releases
<table>
  <tr>
    <th>Date</th>
    <th>Name</th>
    <th>Version</th>
    <th>Kafka</th>
    <th>Comment</th>
  </tr>
  <tr>
    <td>2014-05-28</td>
    <td>kafka-hybris-1</td>
    <td>1</td>
    <td>kafka 0.8.1.1 (scala 2.9.2)</td>
    <td>Initial release - DO NOT USE</td>
  </tr>
  <tr>
    <td>2014-05-28</td>
    <td>kafka-hybris</td>
    <td>2</td>
    <td>kafka 0.8.1.1 (scala 2.9.2)</td>
    <td>-</td>
  </tr>
</table>
