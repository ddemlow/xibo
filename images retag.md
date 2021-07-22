To pull and retag these images for use with IEAM deployment 

the goal is essentially to turn this (in docker image ls) 
xibosignage/xibo-cms                             release-3.0.0   fa1418ec7b2b   3 weeks ago     538MB

into this
ddemlow/dd.edge.scale.xibo.cms                   3.0.0           fa1418ec7b2b   3 weeks ago     538MB

so:  

docker pull xibosignage/xibo-cms:release-3.0.0
docker image tag  xibosignage/xibo-xmr:release-3.0.0 $DOCKER_BASE/$EDGE_OWNER.$EDGE_DEPLOY.cms:3.0.0
docker push $DOCKER_BASE/$EDGE_OWNER.$EDGE_DEPLOY.cms:3.0.0

(using environment variables which should be set - else change as appropriate)

need to do the same for

docker pull xibosignage/xibo-xmr:release-0.8
docker image tag  xibosignage/xibo-xmr:release-0.8 $DOCKER_BASE/$EDGE_OWNER.$EDGE_DEPLOY.xmr:1.5.0
docker push $DOCKER_BASE/$EDGE_OWNER.$EDGE_DEPLOY.xmr:1.5.0

and 

docker pull ianw/quickchart:latest
docker image tag  ianw/quickchart:latest $DOCKER_BASE/$EDGE_OWNER.$EDGE_DEPLOY.ianw:1.5.0
docker push ddemlow/dd.edge.scale.xibo.ianw:1.5.
