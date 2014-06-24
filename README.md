# BOSH Release for kafka

## Table of Contents
* [Usage](#usage)
* [Releases](#releases)
<br />
<br />


### <a name="usage"></a>Usage

To use this bosh release, first upload it to your bosh:

```
bosh target BOSH_HOST
bosh login
git clone ssh://git@stash.hybris.com:7999/idefix/bosh-release-kafka.git
cd bosh-release-kafka
bosh upload release releases/kafka-hybris-2.yml
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
  <tr>
    <td>2014-06-24</td>
    <td>kafka-hybris</td>
    <td>4</td>
    <td>kafka 0.8.1.1 (scala 2.9.2)</td>
    <td>removed riemann-tools and zookeeper package, using them with deployment manifest instead</td>
  </tr>
</table>
